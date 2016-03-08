#정렬

###퀵 정렬
- 재귀적
- 버블정렬이나 삽입 정렬 알고리즘 보다 효율적인 성능
- 원소들을 두개의 리스트로 분리하는 시간 복잡도는 O(n)이고, 각각의 재귀 호출은 각 리스트 숫자의 절반만큼의 횟수만 발생한다.
- 평균적인 성능 O(nlogn)
- 최악 O(n^2)
- pivot을 선택하는 방법에 따라 다르다.

```java
public class Quicksort {

public static List<Integer> quicksort(List<Integer> numbers) {
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

    final List<Integer> sorted = quicksort(lower);

    sorted.add(pivot);
    sorted.addAll(quicksort(higher));

    return sorted;
}

    @Test
    public void testQuicksort() {
        final List<Integer> numbers = Arrays.asList(6, 4, 9, 5);
        final List<Integer> expected = Arrays.asList(4, 5, 6, 9);

        final List<Integer> actual = quicksort(numbers);
        assertEquals(expected, actual);
    }
}
```

###버블 정렬
- 최악의 경우 역순으로 정렬되어 있는 리스트를 정렬할때 O(n^2), 순환할 때마다 하나의 원소만 변경하기 때문
- 최선의 경우 리스트가 이미 정렬되어있을 때 O(n), 원소의 위치가 변경되지 않기 때문에 원소의 위치를 변경하지 않아도 됨

```java
public class BubbleSort {

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

    @Test
    public void testBubble() {
        final int[] numbers = {6, 4, 9, 5};
        final int[] expected = {4, 5, 6, 9};

        bubbleSort(numbers);
        assertArrayEquals(expected, numbers);
    }
}
```