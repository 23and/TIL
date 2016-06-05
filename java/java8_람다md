#java8 Lambda

````java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6);
````
````java
//모든 정수 합계
public int sumAll(List<Integer> numbers) {
    int total = 0;
    for (int number : numbers) {
        total += number;
    }
    return total;
}
````
````java
//짝수 합계
public int sumAll(List<Integer> numbers) {
    int total = 0;
    for (int number : numbers) {
        if (number % 2 == 0) {
            total += number;
        }
    }
    return total;
}
````
//3보다 큰 정수 합계
public int sumAll(List<Integer> numbers) {
    int total = 0;
    for (int number : numbers) {
        if (number > 3) {
            total += number;
        }
    }
    return total;
}
````

````java
//람다 표현식을 사용한다면
public int sumAll(List<Integer> numbers, Predicate<Integer> p) {
    int total = 0;
    for (int number : numbers) {
        if (p.test(number)) {
            total += number;
        }
    }
    return total;
}
````
````java
sumAll(numbers, n -> true);
sumAll(numbers, n -> n % 2 == 0);
sumAll(numbers, n -> n > 3);
````

- 출처 : https://dzone.com/articles/why-we-need-lambda-expressions