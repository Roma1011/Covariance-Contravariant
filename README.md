# Covariance-Contravariant
Explaining


1) Firstly, to clarify order-preserving and order-reversing, we can consider functions of real numbers. The function f(x) = 2 * x is order-preserving as if a < b then f(a) < f(b). On the other hand the function g(x) = -x is order-reversing as _if a < b then g(b) < g(a).
2) These definitions make sense for any partial order.
3) Types have a partial order by sub-typing, so for example Dog <: Animalas Dog is a sub-type of Animal. We can read this as Dog <: Animal means a Dog is an Animal.
4) Now, we can think of parametrized types such as List[_] as functions from types to types. So List is a function that given input a type A has output a type List[A]. In this sense Map[A, B] is a function of two variables, analogous to f(x, y) = 2x + y over real numbers, for example.
5) Covariance: A parametrized type (e.g. List[A]) is covariant just means that it is order-preserving as a function from types to types, i.e., _if A <: B then List[A] <: List[B].
6 ) Collections are naturally covariant, since Dog <: Animal means a Dog is an animal, so a pack of Dogs is also a pack of animals.
7) Contravariant: A parametrized type P[A] is contravariant if it is order reversing as function from types to types, i.e. if A <: B then P[B] <: P[A].
8) An example is P[A] = A => Boolean This is because we can restrict functions, so a function such as isBlack: Animal => Boolean restricts to isBlack: Dog => Boolean, i.e., from Dog <: Animal we get P[Animal] <: P[Dog]. On the other hand, we have earsAreFloppy: Dog => Boolean but this does not give an object earsAreFloppy: Animal => Boolean (what about snakes?)
9) For example, Map[A, B] is a function from two types A and B to the type Map[A, B]. It is covariant in B and contravariant in A, since if AA <: A we can consider only those keys that have type AA to get Map[AA, B] from a Map[A, B]. On thlye other hand, if B <: BB, then values of type B are automatically have type BB, so a Map[A, B] is a Map[A, BB]
10 )Finally, the relation to categories (not needed in this case). We have a category whose objects are types and morphisms are only inclusions between sub-types. From this view, covariance and contravariance are being covariant/contravariant Functors (in general any partially ordered set gives a category, and functors are order-preserving maps).
