#HTTP
- HTTP�� ���ͳ��� ���� �����͸� ��û�ϰ� �ޱ� ���� �ֵ� ��� �� �ϳ��̴�.
- HTTP�� ������̵����� ���� �����ϴµ� ���ȴ�. ����ġ�� HTTPD, ����ũ�μ���Ʈ�� IIS, ��Ĺ ���� HTTP ������ ü�������� ������ ��û�� �����ؼ� ������ ������ �� �� �ֵ��� �����Ǿ� �ִ�.

###HTTP �޼���
```
GET : ��û�� �ڿ��� �����Ѵ�. ������ ����� �Ѵ�.
POST : ��û�� �������� ���� �ڿ��� ������Ʈ�Ѵ�.
PUT : ��û�� �������� ���� �ڿ��� ������ ���� �����Ѵ�.
DELETE : ��û�� �ڿ��� �����Ѵ�.
HEAD : GET ��û�� ��������� ���� �ڵ�� ����� ��ȯ�Ѵ�.
```
###HEAD�� ���� ����
- �ٿ�ε� �ʿ���� ��뷮 �ڿ��� �����ϴ��� Ȯ���ϴµ� ����� �� �ִ�. 
- Ŭ���̾�Ʈ�� ������ �ش��ڿ��� �ٿ�ε� �ߴٸ� ������Ʈ�� �ֽ� �纻�� �ִ����� Ŭ���̾�Ʈ�� �� �� �ְ� **Last-Modified** ����� Ȯ���� �� �ִ�.

###HTTP�����ڵ�
- HTTP ������ ù��° ���� ���� �ڵ带 �����ϸ� �ڵ尡 �ǹ��ϴ� ������ �������� �����Ѵ�.
- ù��° ���ڴ� ����з�, ��� 2xx �ڵ�� ��û�� ������ �������̶�� ���� �˷��ش�.
- 4xx�з��� Ŭ���̾�Ʈ���� ����, ������ ��û�� ������ ���ߴٴ� ���� �˷��ش�.
- 5xx�з��� ���� ���� �̽��� �ִٴ� ���� �˷��ش�. �̰�� ������ ��ġ�� ������ �ʰ����� Ŭ���̾�Ʈ�� ���ܻ�Ȳ�� �ذ��� �� ����.