Product Iterator
=================
This reposity is forked from [here](https://github.com/mirandaconrado/product-iterator)

C++ iterator that performs the cartesian product of many containers.
Requires C++11 and boost.

I have let the test of this reposity be easier than before.
You just do some operations following: 
`$ chmod +x cmp.sh` 
`$ ./cmp.sh` 
`$ ./product_iterator_test.exe` 

And you will get the result like this:
```
a contains: 1 and 3 and 5
a contains: 1 and 3 and 6
a contains: 1 and 3 and 7
a contains: 1 and 3 and 8
a contains: 1 and 4 and 5
a contains: 1 and 4 and 6
a contains: 1 and 4 and 7
a contains: 1 and 4 and 8
a contains: 2 and 3 and 5
a contains: 2 and 3 and 6
a contains: 2 and 3 and 7
a contains: 2 and 3 and 8
a contains: 2 and 4 and 5
a contains: 2 and 4 and 6
a contains: 2 and 4 and 7
a contains: 2 and 4 and 8
```

It's really easy to use Product Iterator API as following codes:

```
vector<int> c1({1,2});
vector<int> c2({3,4});
vector<int> c3({5,6,7,8});
auto it = make_product_iterator(c1, c2, c3);
auto end = it.get_end();
for (; it != end; ++it) {
    // Provides a std::tuple<int,char> with the values from the constructor
    *it;
    // Access to a single element of the tuple is optimized and the following
    // comparison always holds
    // it.get<0>() == std::get<0>(*it);
    std::cout << "a contains: " << std::get<0>(*it);
    std::cout << " and " << std::get<1>(*it);
    std::cout << " and " << std::get<2>(*it) << '\n';  
}
```

Enjoy your coding!
