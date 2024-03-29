## Jupyter

Добавление нового окружения в jupyter
~~~
pip install --user ipykernel
python -m ipykernel install --user --name=<my_env_name>
~~~

Удаление ядра (kernel) из jupyter
~~~
jupyter kernelspec uninstall your_env
~~~

Запуск jupyter в другой директории. Войдите в свойства ярлыка jupyter-> объект -> замените "%USERPROFILE%/" на требуемую директорию. Например
~~~
"D:\PROJECTS\python"
~~~

В случае, если вы используете IDE [DataSpell](https://www.jetbrains.com/ru-ru/dataspell/) от JetBrains,
 операции о добавлению нового окружения и ядра также необходимы, чтобы в IDE корректно отображались доступные окружения.

Конфиги juputer notebook и jupyterlab находятся в следующей директории

~~~
/users/{your_user}/.jupyter
~~~

Для замены пароля в конфиге генерируем скриптом хэш и вносим его в конфиг сервера [guide](https://stackoverflow.com/questions/66063686/set-jupyter-lab-password-encrypted-with-sha-256)

~~~
from notebook.auth import passwd
my_password = "spam-and-eggs"
hashed_password = passwd(passphrase=my_password, algorithm='sha256')
print(hashed_password)
~~~
