## Sciaga

#Array

ary = Array.new    #=> []
Array.new(3)       #=> [nil, nil, nil]
Array.new(3, true) #=> [true, true, true]

Array.new(4) { Hash.new } #=> [{}, {}, {}, {}]

Array({:a => "a", :b => "b"}) #=> [[:a, "a"], [:b, "b"]]

arr = [1, 2, 3, 4, 5, 6]
arr[2]    #=> 3
arr[100]  #=> nil
arr[-3]   #=> 4
arr[2, 3] #=> [3, 4, 5]
arr[1..4] #=> [2, 3, 4, 5]
arr[1..-3] #=> [2, 3, 4]

arr.first #=> 1
arr.last  #=> 6

arr.take(3) #=> [1, 2, 3]
arr.drop(3) #=> [4, 5, 6]

browsers.include?('Konqueror') #=> false

arr = [1, 2, 3, 4]
arr.push(5) #=> [1, 2, 3, 4, 5]
arr << 6    #=> [1, 2, 3, 4, 5, 6]

unshift will add a new item to the beginning of an array.
arr.unshift(0) #=> [0, 1, 2, 3, 4, 5, 6]

arr.insert(3, 'apple')  #=> [0, 1, 2, 'apple', 3, 4, 5, 6]

arr.shift #=> 1
arr #=> [2, 3, 4, 5]

A useful method if you need to remove nil values from an array is compact:
arr = ['foo', 0, nil, 'bar', 7, 'baz', nil]
arr.compact  #=> ['foo', 0, 'bar', 7, 'baz']
arr          #=> ['foo', 0, nil, 'bar', 7, 'baz', nil]
arr.compact! #=> ['foo', 0, 'bar', 7, 'baz']
arr          #=> ['foo', 0, 'bar', 7, 'baz']

Iterating over Arrays
