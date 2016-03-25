#����
- ����� ���������� ��� ����ð��� ���⵵�� O(n2)�̰� �����İ� �������� ��� ����ð��� ���⵵�� O(n log n)�̴�.
- �����Ͱ� 100���� ��� ��� �������α׷��̳� ����� �ð��� �ɸ���. 
- �׷��� �����Ͱ� 1,000,000�� �ִٰ� �����غ��� �˰����� ��� ���ູ�⵵�� O(n2)�� ��� 1,000,000,000,000���� �񱳸� ������ �� �ִ�. ���⵵�� O(n log n)�� ��� 1,000,000 *20������ �پ�� �� �ִ�. 

- ���� ������ �ϱ����� ��ü ��Ƚ�� T(n) = n(n-1)/2 �̴�. �� Ƚ���� ������ ����ð� ���⵵�� O( n(n-1)/2 ) = O(n2)�̴�.
- ���� ������ �ϱ����� ��ü ��Ƚ�� T(n) = n(n-1)/2 �̴�. �� Ƚ���� ������ ����ð� ���⵵�� O(n(n-1)/2 ) = O(n2)�̴�.

###�� ����
- �����
- ���������̳� ���� ���� �˰��� ���� ȿ������ ����
- ���ҵ��� �ΰ��� ����Ʈ�� �и��ϴ� �ð� ���⵵�� O(n)�̰�, ������ ��� ȣ���� �� ����Ʈ ������ ���ݸ�ŭ�� Ƚ���� �߻��Ѵ�.
- ������� ���� O(nlogn)
- �־� O(n^2)
- pivot�� �����ϴ� ����� ���� �ٸ���.

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

###���� ����
- �־��� ��� �������� ���ĵǾ� �ִ� ����Ʈ�� �����Ҷ� O(n^2), ��ȯ�� ������ �ϳ��� ���Ҹ� �����ϱ� ����
- �ּ��� ��� ����Ʈ�� �̹� ���ĵǾ����� �� O(n), ������ ��ġ�� ������� �ʱ� ������ ������ ��ġ�� �������� �ʾƵ� ��

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