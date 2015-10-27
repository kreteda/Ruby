# Sciaga

#Array


##przydatne, nowe
ary = Array.new   
=> []
Array.new(3)       
=> [nil, nil, nil]
Array.new(3, true) 
=> [true, true, true]

Array.new(4) { Hash.new } 
=> [{}, {}, {}, {}]

Array({:a => "a", :b => "b"}) 
=> [[:a, "a"], [:b, "b"]]

arr = [1, 2, 3, 4, 5, 6]
arr[2]    
=> 3
arr[100]  
=> nil
arr[-3]   
=> 4
arr[2, 3] 
=> [3, 4, 5]
arr[1..4] 
=> [2, 3, 4, 5]
arr[1..-3] 
=> [2, 3, 4]
#pierwszy i ostatni element
arr.first 
=> 1
arr.last  
=> 6
##take i drop
arr.take(3) 
=> [1, 2, 3]
arr.drop(3) 
=> [4, 5, 6]
##include?##
browsers.include?('Konqueror') 
=> false

arr = [1, 2, 3, 4]
arr.push(5) 
=> [1, 2, 3, 4, 5]
arr << 6    
=> [1, 2, 3, 4, 5, 6]

##unshift will add a new item to the beginning of an array.
arr.unshift(0) 
=> [0, 1, 2, 3, 4, 5, 6]

##insert
arr.insert(3, 'apple')  
=> [0, 1, 2, 'apple', 3, 4, 5, 6]
#shift
arr.shift 
=> 1
arr 
=> [2, 3, 4, 5]

##A useful method if you need to remove nil values from an array is compact:
arr = ['foo', 0, nil, 'bar', 7, 'baz', nil]
arr.compact  
=> ['foo', 0, 'bar', 7, 'baz']
arr          
=> ['foo', 0, nil, 'bar', 7, 'baz', nil]
arr.compact! 
=> ['foo', 0, 'bar', 7, 'baz']
arr          
=> ['foo', 0, 'bar', 7, 'baz']

arr = [1, 2, 3, 4, 5]
arr.each { |a| print a -= 10, " " }
 prints: -9 -8 -7 -6 -5
=> [1, 2, 3, 4, 5]
##str
words = %w[first second third fourth fifth sixth]
str = ""
words.reverse_each { |word| str += "#{word} " }
p str 
=> "sixth fifth fourth third second first "
##map
arr.map { |a| 2*a }   
=> [2, 4, 6, 8, 10]
arr                   
=> [1, 2, 3, 4, 5]
arr.map! { |a| a**2 } 
=> [1, 4, 9, 16, 25]
arr                   
=> [1, 4, 9, 16, 25]
##przydatne2
Array.[]( 1, 'a', /^A/ ) 
=> [1, "a", /^A/]
Array[ 1, 'a', /^A/ ]    
=> [1, "a", /^A/]
[ 1, 'a', /^A/ ]         
=> [1, "a", /^A/]

[ 1, 1, 3, 5 ] & [ 1, 2, 3 ]                 
=> [ 1, 3 ]
[ 'a', 'b', 'b', 'z' ] & [ 'a', 'b', 'c' ]   
=> [ 'a', 'b' ]

[ 1, 2, 3 ] * 3    
=> [ 1, 2, 3, 1, 2, 3, 1, 2, 3 ]
[ 1, 2, 3 ] * ","  
=> "1,2,3"

[ 1, 2 ] << "c" << "d" << [ 3, 4 ]
=>  [ 1, 2, "c", "d", [ 3, 4 ] ]

a = [ "a", "b", "c", "d", "e" ]
a[2] +  a[0] + a[1]    
=> "cab"
a[6]                   
=> nil
a[1, 2]                
=> [ "b", "c" ]
a[1..3]               
=> [ "b", "c", "d" ]
a[4..7]                
=> [ "e" ]
a[6..10]               
=> nil
a[-3, 3]               
=> [ "c", "d", "e" ]
 special cases
a[5]                   
=> nil
a[6, 1]                
=> nil
a[5, 1]                
=> []
a[5..10]               
=> []

a = Array.new
a[4] = "4";                 
=> [nil, nil, nil, nil, "4"]
a[0, 3] = [ 'a', 'b', 'c' ] 
=> ["a", "b", "c", nil, "4"]
a[1..2] = [ 1, 2 ]          
=> ["a", 1, 2, nil, "4"]
a[0, 2] = "?"               
=> ["?", 2, nil, "4"]
a[0..2] = "A"               
=> ["A", "4"]
a[-1]   = "Z"               
=> ["A", "Z"]
a[1..-1] = nil              
=> ["A", nil]
a[1..-1] = []               
=> ["A"]
a[0, 0] = [ 1, 2 ]          
=> [1, 2, "A"]
a[3, 0] = "B"               
=> [1, 2, "A", "B"]

a = [ "a", "b", "c", "d", "e" ]
a.at(0)     
=> "a"
a.at(-1)    
=> "e"

ary = [0, 4, 7, 10, 12]
 try to find v such that 4 <= v < 8
ary.bsearch {|x| 1 - x / 4 } 
=> 4 or 7
 try to find v such that 8 <= v < 10
ary.bsearch {|x| 4 - x / 2 } 
=> nil

a = [1, 2, 3, 4]
a.combination(1).to_a  
=> [[1],[2],[3],[4]]
a.combination(2).to_a  
=> [[1,2],[1,3],[1,4],[2,3],[2,4],[3,4]]
a.combination(3).to_a  
=> [[1,2,3],[1,2,4],[1,3,4],[2,3,4]]
a.combination(4).to_a  
=> [[1,2,3,4]]
a.combination(0).to_a  
=> [[]] # one combination of length 0
a.combination(5).to_a  
=> []   # no combinations of length 5

#HASH

grades = { "Jane Doe" => 10, "Jim Doe" => 6 }


Hash["a", 100, "b", 200] #=> {"a"=>100, "b"=>200}
Hash[ [ ["a", 100], ["b", 200] ] ] #=> {"a"=>100, "b"=>200}
Hash["a" => 100, "b" => 200] #=> {"a"=>100, "b"=>200}



##wielkosc i typ czcionki

options = { :font_size => 10, :font_family => "Arial" }
rownowznacznie:
options = { font_size: 10, font_family: "Arial" }

##wartosc domyslna

grades = Hash.new(0)


books = {}
books[:matz] = "The Ruby Language"
books[:black] = "The Well-Grounded Rubyist"


##parametry

Person.create(name: "John Doe", age: 27)

def self.create(params)
@name = params[:name]
@age = params[:age]
end


##convert

Hash.try_convert({1=>2}) #=> {1=>2}
Hash.try_convert("1=>2") #=> nil


##clear

h = { "a" => 100, "b" => 200 } #=> {"a"=>100, "b"=>200}
h.clear #=> {}


##petla each

h = { "a" => 100, "b" => 200 }
h.each {|key, value| puts "#{key} is #{value}" }

##empty?

{}.empty? #=> true


##featch

h = { "a" => 100, "b" => 200 }
h.fetch("a") #=> 100
h.fetch("z", "go fish") #=> "go fish"
h.fetch("z") { |el| "go fish, #{el}"} #=> "go fish, z"


##has

h = { "a" => 100, "b" => 200 }
h.has_key?("a") #=> true
h.has_key?("z") #=> false



h = { "a" => 100, "b" => 200 }
h.has_value?(100) #=> true
h.has_value?(999) #=> false


##to_string/to_s

h = { "c" => 300, "a" => 100, "d" => 400, "c" => 300 }
h.to_s #=> "{\"c\"=>300, \"a\"=>100, \"d\"=>400}"


##invert

h = { "n" => 100, "m" => 100, "y" => 300, "d" => 200, "a" => 0 }
h.invert #=> {0=>"a", 100=>"m", 200=>"d", 300=>"y"}


##lenght

h = { "d" => 100, "a" => 200, "v" => 300, "e" => 400 }
h.length #=> 4


##merage, polaczenie

h1 = { "a" => 100, "b" => 200 }
h2 = { "b" => 254, "c" => 300 }
h1.merge!(h2) #=> {"a"=>100, "b"=>254, "c"=>300}


##SELECT

h = { "a" => 100, "b" => 200, "c" => 300 }
h.select {|k,v| k > "a"} #=> {"b" => 200, "c" => 300}
h.select {|k,v| v < 200} #=> {"a" => 100}


##shift, usuwanie

h = { 1 => "a", 2 => "b", 3 => "c" }
h.shift #=> [1, "a"]
h #=> {2=>"b", 3=>"c"}


##to array, to_a

h = { "c" => 300, "a" => 100, "d" => 400, "c" => 300 }
h.to_a #=> [["c", 300], ["a", 100], ["d", 400]]

#ENUMERABLE


##all? [{ |obj| block } ] → true or false

%w[ant bear cat].all? { |word| word.length >= 3 } => true
%w[ant bear cat].all? { |word| word.length >= 4 } => false
[nil, true, 99].all? => false


##any? [{ |obj| block }] → true or false

%w[ant bear cat].any? { |word| word.length >= 3 } => true
%w[ant bear cat].any? { |word| word.length >= 4 } => true
[nil, true, 99].any? => true


##hunk { |elt| ... } → an_enumerator, podzial na czesci


[3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5].chunk { |n|
n.even?
}.each { |even, ary|
p [even, ary]
}
=> [false, [3, 1]]
=> [true, [4]]
=> [false, [1, 5, 9]]
=> [true, [2, 6]]
=> [false, [5, 3, 5]]


File.foreach("README").chunk { |line|
/\A\s*\z/ !~ line || nil
}.each { |_, lines|
pp lines
}


##count → int, zliczanie


ary = [1, 2, 4, 2]
ary.count => 4
ary.count(2) => 2
ary.count{ |x| x%2==0 } => 3


##cycle(n=nil) → an_enumerator, petla

a = ["a", "b", "c"]
a.cycle { |x| puts x } => print, a, b, c, a, b, c,.. forever.
a.cycle(2) { |x| puts x } => print, a, b, c, a, b, c.


##drop

a = [1, 2, 3, 4, 5, 0]
a.drop(3) => [4, 5, 0]


##each_cons(n) → an_enumerator, iteruje zadany blok i zwraca n-elementow
(1..10).each_cons(3) { |a| p a }
=> outputs below
[1, 2, 3]
[2, 3, 4]
[3, 4, 5]
[4, 5, 6]
[5, 6, 7]
[6, 7, 8]
[7, 8, 9]
[8, 9, 10]


##each_slice(n) → an_enumerator, dzieli blok na n-elementowe tablice
(1..10).each_slice(3) { |a| p a }
=> outputs below
[1, 2, 3]
[4, 5, 6]
[7, 8, 9]
[10]


##map
(1..4).map { |i| i*i } => [1, 4, 9, 16]
