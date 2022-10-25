Interview Questions

1. Square the list of numbers and then filter out numbers greater than 10 and then find the average
```
List<Integer> list = Arrays.asList(1,2,3,4,5); 
list.stream().mapToInt(i -> i* i).filter(square -> square > 10).average();
```
2. Sort a list of numbers
```
list.stream().sorted()
```
3. Find the lowest and highest numbers of a list
```
list.stream().max(Comparator.comparing(Integer:: valueOf));
```
4. Concatenate two streams
```
Stream.concat(list1.stream(), list1.stream())
```
5. Remove duplicate elements from list
```
list.stream().distinct().collect(Collectors.toList());
```
6. All the even numbers in the list
```
IntStream.range(1,11).filter( i -> i%2 ==0).forEach(System.out::println);
```
7. Find the duplicate elemnts
```
Set<Integer> set - new HashSet<>();
list.stream().filter(i -> !set.add(i)).forEach();

set.add() returns false if element is already present
```
8. Calculate frequency of each word in a given String or caluclate how many times a number is appearing in a list
```
Map<String,Long> map = list.stream().collect(Collectors.groupingBy(Function.identity(), Collectors.counting()));


```
9. Sort list of Employess based on Salary
```
empList.stream().sorted((a,b) -> ( b.getSalary() - a.getSalary())).collect(Collectors.toList());
```
10. Third largest emp salary from list of Employees
```
empList.stream().sorted((a,b) -> ( b.getSalary() - a.getSalary())).skip(3).findFirst();

To get name

empList.stream().sorted((a,b) -> ( b.getSalary() - a.getSalary())).skip(3).map(Employee :: getName).findFirst();
```
