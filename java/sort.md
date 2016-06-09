#정렬
- 버블과 삽입정렬은 평균 수행시간의 복잡도가 O(n2)이고 퀵정렬과 힙정렬은 평균 수행시간의 복잡도가 O(n log n)이다.
- 데이터가 100개인 경우 어느 정렬프로그램이나 비슷한 시간이 걸린다. 
- 그러나 데이터가 1,000,000개 있다고 가정해보자 알고리즘의 평균 수행복잡도가 O(n2)일 경우 1,000,000,000,000번의 비교를 예상할 수 있다. 복잡도가 O(n log n)일 경우 1,000,000 *20번으로 줄어들 수 있다. 

- 버블 정렬을 하기위한 전체 비교횟수 T(n) = n(n-1)/2 이다. 비교 횟수로 따지면 수행시간 복잡도는 O( n(n-1)/2 ) = O(n2)이다.
- 삽입 정렬을 하기위한 전체 비교횟수 T(n) = n(n-1)/2 이다. 비교 횟수로 따지면 수행시간 복잡도는 O(n(n-1)/2 ) = O(n2)이다.

###퀵 정렬
- 재귀적
- 버블정렬이나 삽입 정렬 알고리즘 보다 효율적인 성능
- 원소들을 두개의 리스트로 분리하는 시간 복잡도는 O(n)이고, 각각의 재귀 호출은 각 리스트 숫자의 절반만큼의 횟수만 발생한다.
- 평균적인 성능 O(nlogn)
- 최악 O(n^2)
- pivot을 선택하는 방법에 따라 다르다.
```java
public List<Integer> quickSort(List<Integer> numbers) {
    if (numbers.size() < 2) {
        return numbers;
    }

    final Integer pivot = numbers.get(0);
    final List<Integer> lower = new ArrayList<>();
    final List<Integer> higher = new ArrayList<>();

    for (int i = 1; i < numbers.size(); i++) {
        if (numbers.get(i) < pivot) {
            lower.add(numbers.get(i));
        } else {
            higher.add(numbers.get(i));
        }
    }

    final List<Integer> sorted = quickSort(lower);

    sorted.add(pivot);
    sorted.addAll(quickSort(higher));

    return sorted;
}
```

###버블 정렬
- 최악의 경우 역순으로 정렬되어 있는 리스트를 정렬할때 O(n^2), 순환할 때마다 하나의 원소만 변경하기 때문
- 최선의 경우 리스트가 이미 정렬되어있을 때 O(n), 원소의 위치가 변경되지 않기 때문에 원소의 위치를 변경하지 않아도 됨
- 버블 정렬 개선 : 무회전인 경우 정렬 중단
```java
public void bubbleSort(int[] numbers) {
    boolean numbersSwitched;
    do {
        numbersSwitched = false;
        for (int i = 0; i < numbers.length - 1; i++) {
            if (numbers[i + 1] < numbers[i]) {
                int tmp = numbers[i + 1];
                numbers[i + 1] = numbers[i];
                numbers[i] = tmp;
                numbersSwitched = true;
            }
        }
    } while (numbersSwitched);
}
```

###삽입정렬
````java
public void insertionSort(List<Integer> numbers){
	for(int i=0; i<numbers.size(); i++){
		int start = i;
		while(start > 0 && numbers.get(start-1) > numbers.get(start)){
			swap(numbers, start, start-1);
			start--;
		}
	}
}

public void swap(List<Integer> numbers, int i, int j){
	int temp = numbers.get(i);
	numbers.set(i, numbers.get(j));
	numbers.set(j, temp);
}
````

###선택정렬
````java
public void selectionSort(List<Integer> numbers){
	for(int i=0; i<numbers.size(); i++){
		int minIndex = i;
		for(int j=i+1; j<numbers.size(); j++){
			if(numbers.get(minIndex) > numbers.get(j))
			minIndex = j;
		}
	swap(numbers, i, minIndex);
	}
}
````
