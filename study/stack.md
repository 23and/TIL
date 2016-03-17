#���� (Stack)
- top �̶�� �ϴ� ����Ʈ�� ���� �������� ���԰� ������ �Ͼ�� �ڷᱸ��
- �ڷ��� ���Լ��� (last-in-first-out) ���
- TOP : �ڷ��� ���԰� ������ �̷������ ���ð����� ��ġ�� ǥ���ϴ� ������
- PUSH : ���ÿ��� �ڷ��� ����
- POP : ���ÿ��� �ڷ��� ����
- �ڷ��� ����: TOP = TOP + 1 
- �ڷ��� ����: TOP = TOP - 1
- Overflow �߻� : ������ ũ�Ⱑ M �϶�, TOP > M �̸� Overflow �߻�

###������ �뵵 
- ���ͷ�Ʈ�� ó��
- ������ ��� (����� ǥ��)
- �����ƾ�� ���͹��� ���� (�Լ� ȣ���� ���� ����)

###���� �˰���
```
Top = Top + 1
If(Top > M) Then
            Stack_overflow
Else
            Stack(top) �� data
```

###���� �˰���
```
If(Top = 0) Then
            Stack_underflow
Else
            data �� Stack(top)
            top = top - 1
```


