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


