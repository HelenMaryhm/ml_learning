# Clonable
- shallow copy/deep copy
- super.clone() gives shallow copy.

@Override
public Object clone() {
    try {
        return (Address) super.clone();
    } catch (CloneNotSupportedException e) {
        return new Address(this.street, this.getCity(), this.getCountry());
    }
}


@Override
public Object clone() {
    User user = null;
    try {
        user = (User) super.clone();
    } catch (CloneNotSupportedException e) {
        user = new User(
          this.getFirstName(), this.getLastName(), this.getAddress());
    }
    user.address = (Address) this.address.clone();
    return user;
}


