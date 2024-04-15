# Serializable

- To achieve deep copy, can serialize and object and then deserialize it to new object.
- If a class isn't serializalbe, SerializationException is thrown.


# Method 1

@Test
public void whenModifyingOriginalObject_thenCommonsCloneShouldNotChange() {
    Address address = new Address("Downing St 10", "London", "England");
    User pm = new User("Prime", "Minister", address);
    User deepCopy = (User) SerializationUtils.clone(pm);

    address.setCountry("Great Britain");

    assertThat(deepCopy.getAddress().getCountry())
      .isNotEqualTo(pm.getAddress().getCountry());
}

# Method 2

@Test
public void whenModifyingOriginalObject_thenJacksonCopyShouldNotChange() 
  throws IOException {
    Address address = new Address("Downing St 10", "London", "England");
    User pm = new User("Prime", "Minister", address);
    ObjectMapper objectMapper = new ObjectMapper();
    
    User deepCopy = objectMapper
      .readValue(objectMapper.writeValueAsString(pm), User.class);

    address.setCountry("Great Britain");

    assertThat(deepCopy.getAddress().getCountry())
      .isNotEqualTo(pm.getAddress().getCountry());
}