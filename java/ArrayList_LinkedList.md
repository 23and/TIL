#ArrayList vs LinkedList
- �Ѵ� ����Ʈ �������̽��� �����ߴ�.

###ArrayList
- ���Ұ� �迭
- int[] array
- get(index) �� ���Ͽ� �ش� ���ҿ� �ٷ� ���� �����ϹǷ� O(1)
- �޸� ����� ����ȭ�ϱ� ���� ��� ũ�� ������ �ʿ��� ��쿡 �迭 ��ü�� �����ϴ� O(n) �� �ɸ���.
- �ڹٴ� �����̾Ƽ ť�� �׷����� ���ο��� Object[] ���� �ִ� �ڷᱸ������ ����, �׷��Ƿ� initial size ���� Ŀ���� �翬�� ������ ���̰�  �� ��� O(n)
- ArrayList���� ������ ����, list�� ���ͷ��� �ϴ� ���߿� ���Ҹ� ���� concurrent modification exception�� �ɸ���. (���� ���Ҹ� ���� �� ���� ���߿� �߰����� ���顦index�� �� ã���ϱ�.)
 - �����ϴ� ��� : array�� �տ��� ���� ����, �ٽ� �ڿ��� ���̸鼭 array�� ����?

###LinkedList
- ���ҵ��� ���
- Node {int data; Node prev; Node next;}
- �ش� ������ ��ũ�� Ÿ�� �����ϹǷ� O(n) �� �ɸ���.
- add() �� remove() �� �ش� ��带 �����ϰų� ���ְ� ��ũ�� �����ϸ� �Ǳ⿡ O(1) ���� ��������� ������.