tohoho�̎��H

https://bty.sakura.ne.jp/wp/archives/1075

admin�G���A��admin/admin



��Django �Ƃ�
�@����Ȃ̂Łi���j
������
�@�i���jDjango�́uDjango Girls�v�Ɠ����o�[�W����
���C���X�g�[��
�@Windows�Ȃ̂ňقȂ�
�@python�̓C���X�g�[���ςƂ���
�@django�́uDjango Girls�v�Ɠ����菇�ŃC���X�g�[��
�@�@�E�f�B���N�g���쐬�F> mkdir tohoho
�@�@�E���z���쐬�F> python -m venv myvenv
�@�@�E���z���N���F> myvenv\Scripts\activate
�@�@�Epip��upgrade�F> python -m pip install --upgrade pip
�@�@�Erequirements.txt�iDjango~=3.2.10�j���쐬
�@�@�E�C���X�g�[���F> pip install -r requirements.txt�@�@�@�@>

��SQLite3���o�[�W�����A�b�v����
�@�i���jWindows�Ȃ̂�
�@��������q�̃��f����̊m�F��
�@sqlite-tools-win32-x86-3400100.zip�̒���sqlite3.exe��manae.py�Ɠ����ꏊ�ɃR�s�[����
�@���p�X���ʂ����ꏊ�ɒu���΂������A

���v���W�F�N�g���쐬����
�@��config �Ƃ������O�Ńv���W�F�N�g���쐬���A���̌�A�f�B���N�g������ύX����̂���������
�@�̎菇�Ƃ���

�@> django-admin startproject config
�@> rename ./config ./myproj
�@> cd ./myproj


���ȈՃT�[�o���N������
�P�j./config/settings.py��ҏW
�@�@ALLOWED_HOSTS = ['*']

�Q�j�N��
�@> python manage.py runserver 0.0.0.0:80

���u���E�U����m�F����
�@http://localhost/


���A�v���P�[�V�������쐬����

> python manage.py startapp books

�E./books/urls.py ��V�K�ɍ쐬
�E./books/views.py �r���[�� list_books() ������
�E./config/settings.py �� INSTALLED_APPS �� ./books/apps.py �ɒ�`���ꂽ�N���X��o�^
�E./config/urls.py �ɁAhttp://server/books/ ���v�����ꂽ��A./books/urls.py ���Q�Ƃ���悤�Ɏw��


���A�v���P�[�V�����f�B���N�g�����W�񂷂�

> mkdir ./apps

�E./config/settings.py �� ./apps �f�B���N�g����o�^
�E$ mv ./books ./apps

���u���E�U����m�F����
�@http://localhost/books/

�����f�����쐬����

�E./apps/books/models.py�ɒǋL

> python manage.py makemigrations
> python manage.py migrate

�m�F

> python manage.py dbshell
���P�j

sqlite> .tables
sqlite> .schema books_book
sqlite> select * from books_book; 

���Ǘ��҃T�C�g���g�p����

> python manage.py createsuperuser

��admin/admin�ɂ��܂���

�E./apps/books/admin.py��ҏW���Ǘ��҃T�C�g�ŕҏW�ł���悤�ɒǋL

���u���E�U����m�F����i�f�[�^���o�^�j
�@http://localhost/admin/


���e���v���[�g���g�p����
���e���v���[�g�ŋ��ʂȃ��C�A�E�g�y�[�W���Q�Ƃ���
���X�^�e�B�b�N�t�@�C����ǂݍ���
���w�b�_�⃁�j���[�o�[��\������
���ڍ׉��
���ҏW���
��������Ή�
������ݒ��ʂ�p�ӂ���
��Apache����N������
��MariaDB�Ɛڑ�����


