# STL Notes

```cpp
    /*------*/
    // ARRAY //
    /*------*/

    // init arr of size 5 with all 0
    array<int, 5> arr1 = {0};
    int arr2[5] = {};

    // fill array with 2
    array<int, 5> arr3;
    arr3.fill(3);

    // access element at 2nd index
    array<int, 5> arr4 = {1, 2, 3, 4, 5};
    arr4.at(2);

    // iterate through array
    array<int, 5> arr5 = {1, 2, 3, 4, 5};
    for(auto i : arr5){
        cout << i << endl;
    }

    // begin is the address of the first element of the array
    cout << arr5.begin() << endl;
    // end is the address after the last element of the array
    cout << arr5.end() << endl;

    // size of array
    arr5.size();

    // front is the first element of the array
    cout << arr5.front() << endl;

    // back is the last element of the array
    cout << arr5.back() << endl;

    // swap two arrays
    array<int, 5> arr6 = {1, 2, 3, 4, 5};
    array<int, 5> arr7 = {6, 7, 8, 9, 10};
    arr6.swap(arr7);

    // sort array
    array<int, 5> arr8 = {5, 4, 3, 2, 1};
    sort(arr8.begin(), arr8.end());

    // reverse array
    array<int, 5> arr9 = {1, 2, 3, 4, 5};
    reverse(arr9.begin(), arr9.end());

    // check if array is sorted
    array<int, 5> arr10 = {1, 2, 3, 4, 5};
    is_sorted(arr10.begin(), arr10.end());

    // check if array is empty
    array<int, 5> arr11 = {1, 2, 3, 4, 5};
    arr11.empty();

    /*--------*/
    // VECTOR //
    /*--------*/

    vector<int> vec1 = {};
    // add element to vector
    vec1.push_back(1);
    vec1.push_back(2);
    // remove element from end
    vec1.pop_back();

    // clear vector
    vec1.clear();

    // insert 2 at all 5 indices
    vector<int> vec2(5, 2);

    // copy vector
    vector<int> vec3(vec2);
    vector<int> vec4(vec2.begin(), vec2.end()); // [) = include first index, exclude last index

    // slice vector
    vector<int> vec5 = {1, 2, 3, 4, 5};
    // vec5.begin() = 1st index // 1
    // vec5.begin() + 2 = 3rd index so 3rd is excluded // 2
    vector<int> vec6(vec5.begin(), vec5.begin() + 2); // 1,2

    // iterate through vector
    vector<int> vec7 = {1, 2, 3, 4, 5};
    for(auto i : vec7){
        cout << i << endl;
    }

    // 2d vector
    vector<vector<int>> vec8 = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    // access element at 2nd row, 3rd column
    vec8[1][2];
    // iterate through 2d vector
    for(auto i : vec8){
        for(auto j : i){
            cout << j << endl;
        }
    }

    // define vector of size 5x10 with all 0
    vector<vector<int>> vec9(5, vector<int>(10, 0));

    /*-------------*/
    // ORDERED SET //
    /*-------------*/

    // init set
    // set store int in sorted order // Big O(log n)
    set<int> s1 = {1, 2, 3, 4, 5};

    // insert element
    s1.insert(6); // 6
    s1.insert(6); // 6
    s1.insert(4); // 6, 4
    s1.insert(7); // 6, 4, 7
    s1.insert(8); // 6, 4, 7, 8
    s1.insert(9); // 6, 4, 7, 8, 9
    s1.insert(10);// 6, 4, 7, 8, 9, 10

    // erase element
    s1.erase(6); // 4, 7, 8, 9, 10
    s1.erase(s1.begin()); // 7, 8, 9, 10
    s1.erase(s1.begin(), s1.end()); // empty

    // iterate through set
    set<int> s2 = {1, 2, 3, 4, 5};
    for(auto i : s2){
        cout << i << endl;
    }

    // find element
    set<int> s3 = {1, 2, 3, 4, 5};
    s3.find(3); // 3
    s3.find(6); // s3.end() // cos 6 is not in set

    // check if element is in set
    set<int> s4 = {1, 2, 3, 4, 5};
    s4.count(3); // 1
    s4.count(6); // 0


    /*---------------*/
    // UNORDERED SET //
    /*---------------*/

    // init set
    // unordered set store int in random order // Big O(1)
    unordered_set<int> us1 = {1, 2, 3, 4, 5};

    // insert element
    us1.insert(6); // 6
    us1.insert(6); // 6
    us1.insert(4); // 6, 4
    us1.insert(7); // 6, 4, 7
    us1.insert(8); // 6, 4, 7, 8

    /*----------*/
    // MULTISET //
    /*----------*/

    // init multiset
    // multiset store int in sorted order // Big O(log n)
    multiset<int> ms1 = {1, 2, 3, 4, 5};

    // insert element
    ms1.insert(6); // 1, 2, 3, 4, 5, 6
    ms1.insert(6); // 1, 2, 3, 4, 5, 6, 6
    ms1.insert(4); // 1, 2, 3, 4, 4, 5, 6, 6

    // erase element
    ms1.erase(6); // 1, 2, 3, 4, 4, 5
    ms1.erase(ms1.begin()); // 2, 3, 4, 4, 5

    // find
    multiset<int> ms2 = {1, 2, 3, 4, 5};
    auto ms_it = ms2.find(3); // 3
    ms2.erase(ms_it); // 1, 2, 4, 5


    /*-----*/
    // MAP //
    /*-----*/

    // init map
    // map store key value pair in sorted order // Big O(log n)
    map<string, int> m1 = {{"a", 1}, {"b", 2}, {"c", 3}};
    // access value
    m1["a"]; // 1
    m1["b"]; // 2
    m1["c"]; // 3

    // insert element
    m1["d"] = 4; // {"a", 1}, {"b", 2}, {"c", 3}, {"d", 4}
    m1["d"] = 5; // {"a", 1}, {"b", 2}, {"c", 3}, {"d", 5}

    // erase element
    m1.erase("d"); // {"a", 1}, {"b", 2}, {"c", 3}

    // iterate through map
    map<string, int> m2 = {{"a", 1}, {"b", 2}, {"c", 3}};
    for(auto i : m2){
        cout << i.first << " " << i.second << endl;
    }

    // change value
    map<string, int> m3 = {{"a", 1}, {"b", 2}, {"c", 3}};
    m3["a"] = 4; // {"a", 4}, {"b", 2}, {"c", 3}
    m3.emplace("a", 5); // {"a", 5}, {"b", 2}, {"c", 3}

    // clear map
    map<string, int> m4 = {{"a", 1}, {"b", 2}, {"c", 3}};
    m4.clear(); // empty


    /*-------------*/
    // UNORDERED MAP //
    /*-------------*/

    // init unordered map
    // unordered map store key value pair in random order // Big O(1)
    unordered_map<string, int> um1 = {{"a", 1}, {"b", 2}, {"c", 3}};
    // access value
    um1["a"]; // 1
    um1["b"]; // 2

    // insert element
    um1["d"] = 4; // {"a", 1}, {"b", 2}, {"c", 3}, {"d", 4}

    // erase element
    um1.erase("d"); // {"a", 1}, {"b", 2}, {"c", 3}


    /*----------*/
    // MULTIMAP //
    /*----------*/

    // init multimap
    // multimap store key value pair in sorted order // Big O(log n)
    multimap<string, int> mm1 = {{"a", 1}, {"a", 2}, {"c", 3}};

    // emplace
    mm1.emplace("a", 4); // {"a", 1}, {"a", 2}, {"a", 4}, {"c", 3}

    // erase element
    mm1.erase("a"); // {"c", 3}

    // find
    multimap<string, int> mm2 = {{"a", 1}, {"a", 2}, {"c", 3}};
    auto mm_it = mm2.find("a"); // {"a", 1}
    mm2.erase(mm_it); // {"a", 2}, {"c", 3}

    // clear map
    multimap<string, int> mm3 = {{"a", 1}, {"a", 2}, {"c", 3}};
    mm3.clear(); // empty


    /*-------*/
    // STACK //
    /*-------*/ 

    // init stack
    // lifo
    stack<int> st1;
    st1.push(1); // 1
    st1.push(2); // 1, 2
    st1.push(3); // 1, 2, 3

    // pop
    st1.pop(); // 1, 2

    // top
    st1.top(); // 2

    // empty
    st1.empty(); // false

    // size
    st1.size(); // 2


    /*-------*/
    // QUEUE //
    /*-------*/

    // init queue
    // fifo
    queue<int> q1;
    q1.push(1); // 1
    q1.push(2); // 1, 2
    q1.push(3); // 1, 2, 3

    // pop
    q1.pop(); // 2, 3
    
    // front
    q1.front(); // 2

    // back
    q1.back(); // 3

    // check if empty
    q1.empty(); // false

    // size
    q1.size(); // 2


    /*----------------*/
    // PRIORITY QUEUE //
    /*----------------*/

    // init priority queue
    // max heap
    priority_queue<int> pq1;
    pq1.push(1); // 1
    pq1.push(2); // 2, 1
    pq1.push(3); // 3, 2, 1

    // pop
    pq1.pop(); // 2, 1

    // top
    pq1.top(); // 2


    /*------*/
    // LIST //
    /*------*/

    // init list
    list<int> l1 = {1, 2, 3, 4, 5};

    // insert element
    l1.push_back(6); // 1, 2, 3, 4, 5, 6    
    l1.push_front(0); // 0, 1, 2, 3, 4, 5, 6

    // erase element
    l1.pop_back(); // 0, 1, 2, 3, 4, 5
    l1.pop_front(); // 1, 2, 3, 4, 5

    // insert element
    l1.insert(l1.begin(), 0); // 0, 1, 2, 3, 4, 5
    l1.insert(l1.end(), 6); // 0, 1, 2, 3, 4, 5, 6

    // erase element
    l1.erase(l1.begin()); // 1, 2, 3, 4, 5, 6
    l1.erase(l1.end()); // 1, 2, 3, 4, 5

    // clear list
    l1.clear(); // empty

    // iterate through list
    list<int> l2 = {1, 2, 3, 4, 5};
    for(auto i : l2){
        cout << i << endl;
    }

    // reverse list
    list<int> l3 = {1, 2, 3, 4, 5};
    l3.reverse(); // 5, 4, 3, 2, 1

    // sort list
    list<int> l4 = {5, 4, 3, 2, 1};
    l4.sort(); // 1, 2, 3, 4, 5

    // remove element
    list<int> l5 = {1, 2, 3, 4, 5};
    l5.remove(3); // 1, 2, 4, 5

    // unique element
    list<int> l6 = {1, 1, 2, 3, 4, 5};
    l6.unique(); // 1, 2, 3, 4, 5

    // merge list
    list<int> l7 = {1, 2, 3};
    list<int> l8 = {4, 5, 6};
    l7.merge(l8); // 1, 2, 3, 4, 5, 6

    // splice list
    list<int> l9 = {1, 2, 3};
    list<int> l10 = {4, 5, 6};
    l9.splice(l9.begin(), l10); // 4, 5, 6, 1, 2, 3



    /*--------*/
    // BITSET //
    /*--------*/

    // init bitset
    bitset<8> b1; // 00000000
    bitset<8> b2(5); // 00000101

    // set bit
    b1.set(0); // 00000001
    b1.set(1); // 00000011

    // reset bit
    b1.reset(0); // 00000010
    b1.reset(1); // 00000000

    // flip bit
    b1.flip(0); // 00000001


    // all
    // if all bits are 1 return true
    // if any bit is 0 return false
    b1.all(); // false

    // any
    // if any bit is 1 return true
    // if all bits are 0 return false
    b1.any(); // true

    // count
    // return number of 1 bits
    b1.count(); // 1

    // flip
    // flip all bits
    // 00000001 -> 11111110
    b1.flip(); // 11111110

    // none
    // if all bits are 0 return true
    // if any bit is 1 return false
    b1.none(); // false

    // size
    // return number of bits
    b1.size(); // 8

    // test
    // return true if bit is 1
    // return false if bit is 0
    b1.test(0); // true

    // set
    // set all bits to 1
    b1.set(); // 11111111
    b1.set(0, 0); // 11111110
    b1.set(1, 0); // 11111100

    // reset
    // set all bits to 0
    b1.reset(); // 00000000



    /*-------*/
    // ALGOS //
    /*-------*/

    // sort
    vector<int> v1 = {5, 4, 3, 2, 1};

    // sort in ascending order
    sort(v1.begin(), v1.end()); // 1, 2, 3, 4, 5

    // sort in descending order
    sort(v1.begin(), v1.end(), greater<int>()); // 5, 4, 3, 2, 1

    // reverse
    vector<int> v2 = {1, 2, 3, 4, 5};
    reverse(v2.begin(), v2.end()); // 5, 4, 3, 2, 1

    // max
    vector<int> v3 = {1, 2, 3, 4, 5};
    max(v3.begin(), v3.end()); // 5

    // min
    vector<int> v4 = {1, 2, 3, 4, 5};
    min(v4.begin(), v4.end()); // 1

    // max_element
    vector<int> v5 = {1, 2, 3, 4, 5};
    max_element(v5.begin(), v5.end()); // 5

    // min_element
    vector<int> v6 = {1, 2, 3, 4, 5};
    min_element(v6.begin(), v6.end()); // 1

    // accumulate
    // sum of all elements
    vector<int> v7 = {1, 2, 3, 4, 5};
    accumulate(v7.begin(), v7.end(), 0); // 15

    // count
    // count number of elements equal to 3
    vector<int> v8 = {1, 2, 3, 3, 4, 5};
    count(v8.begin(), v8.end(), 3); // 2

    // count_if
    // count number of elements greater than 3
    vector<int> v9 = {1, 2, 3, 4, 5};
    count_if(v9.begin(), v9.end(), [](int x){return x > 3;}); // 2

    // find
    // find first element equal to 3
    vector<int> v10 = {1, 2, 3, 4, 5};
    find(v10.begin(), v10.end(), 3); // 3

    // find_if
    // find first element greater than 3
    vector<int> v11 = {1, 2, 3, 4, 5};
    find_if(v11.begin(), v11.end(), [](int x){return x > 3;}); // 4

    // binary_search
    // check if 3 is present in vector
    vector<int> v12 = {1, 2, 3, 4, 5};
    binary_search(v12.begin(), v12.end(), 3); // true

    // lower_bound
    // find first element greater than or equal to 3
    vector<int> v13 = {1, 2, 3, 4, 5};
    lower_bound(v13.begin(), v13.end(), 3); // 3

    // upper_bound
    // find first element greater than 3
    vector<int> v14 = {1, 2, 3, 4, 5};
    upper_bound(v14.begin(), v14.end(), 3); // 4

    // equal
    // check if two vectors are equal
    vector<int> v15 = {1, 2, 3, 4, 5};
    vector<int> v16 = {1, 2, 3, 4, 5};
    equal(v15.begin(), v15.end(), v16.begin()); // true

    // is_permutation
    // check if two vectors are permutation of each other
    vector<int> v17 = {1, 2, 3, 4, 5};
    vector<int> v18 = {5, 4, 3, 2, 1};
    is_permutation(v17.begin(), v17.end(), v18.begin()); // true

    // permutation
    // generate all permutations of vector
    vector<int> v19 = {1, 2, 3};
    do {
        for (int x : v19) {
            cout << x << " ";
        }
        cout << endl;
    } while (next_permutation(v19.begin(), v19.end()));

    // 1 2 3
    // 1 3 2
    // 2 1 3
    // 2 3 1
    // 3 1 2
    // 3 2 1

    // prev_permutation
    // generate all permutations of vector in reverse order
    vector<int> v20 = {1, 2, 3};
    do {
        for (int x : v20) {
            cout << x << " ";
        }
        cout << endl;
    } while (prev_permutation(v20.begin(), v20.end()));

    // 3 2 1
    // 3 1 2
    // 2 3 1
    // 2 1 3
    // 1 3 2
    // 1 2 3


    /*------------*/
    // COMPARATOR //
    /*------------*/

    // comparator
    // compare two objects
    // return true if first object is smaller
    // return false if first object is greater

    // sort in ascending order
    sort(v1.begin(), v1.end(), [](int x, int y){return x < y;}); // 1, 2, 3, 4, 5

    // sort in descending order
    sort(v1.begin(), v1.end(), [](int x, int y){return x > y;}); // 5, 4, 3, 2, 1

    // max
    max(v3.begin(), v3.end(), [](int x, int y){return x < y;}); // 5

    // min
    min(v4.begin(), v4.end(), [](int x, int y){return x < y;}); // 1

    // max_element
    max_element(v5.begin(), v5.end(), [](int x, int y){return x < y;}); // 5

    // min_element
    min_element(v6.begin(), v6.end(), [](int x, int y){return x < y;}); // 1



    // lambda function in C++
    // [] (int x, int y) {return x + y;}
    // [] -> capture list
    // (int x, int y) -> parameters
    // {return x + y;} -> body

```
