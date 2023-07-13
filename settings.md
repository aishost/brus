# Изменения файла settings.py

### в вверху файла прописываем import os

### После строки STATIC_URL = "static/" нужно дополнить код:

#### Куда складывать статику (css, js и прочее)
    STATIC_ROOT = os.path.join(BASE_DIR, 'static')

#### url доступа к загруженым пользователями файлам.
    MEDIA_URL = '/media/'

#### папка куда будут складываться загруженный пользователями контент 
    MEDIA_ROOT = os.path.join(BASE_DIR, 'media')

#### утилиты, которые не требуют нашего вмешательства, улучшают работу статики
    STATICFILES_FINDERS = [
        "django.contrib.staticfiles.finders.FileSystemFinder",
        "django.contrib.staticfiles.finders.AppDirectoriesFinder",
    ]

#### Какие файлы мы хотим сделать ещё статическими укажем здесь
    STATICFILES_DIRS = [
    #os.path.join(BASE_DIR, "other_static"),
    ]
