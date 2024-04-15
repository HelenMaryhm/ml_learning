# Marker Interface/tagging Interface
- Doesn't have methods or constants inside.
- Provides runtime information about objects.
- e.g. Serializable, Cloneable, Remote interface.

# Cloneable Interface
- CloneNotSupportedException.
- Indicator that Object.clone() can be called.

# Serializable Interface
- NotSerializableException.

# Custom Marker Interface
- e.g. Deleteable
- class A implements Deletable{}
- object instanceof Deletable

# Annotations (VS) Marker Interface
- This allows polymorphism. (Annotations don't)
- e.g. interface Shape  ->  marker interface DeletableShape (extends Shape)  ->  Rectangle implements DeletableShaoe  ->  if object instanceof DeletableShape.

