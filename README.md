## Разворачивание проекта

### Ставим Python 310 (Не забудьте поставить галочку "add to PATH")
https://www.python.org/ftp/python/3.10.11/

### Создать виртуальное окружение
`python -m venv venv`

### Активировать виртуальное окружение
Шиндоус:  
`venv\Scripts\activate.bat`  
Для PowerShell  
`venv\Scripts\Activate.ps1`  
Линукс:  
`source venv/bin/activate`

### Установить зависимости
`pip install -r requirements.txt`

### Если не планируете самостоятельно собирать библиотеки, уже собранные для 64 винды хранятся в `extensions/build_lib`
`xcopy extensions\build_lib\* venv\Lib\site-packages\ /E /I`  


## Разворачивание для сборки расширений

### Ставим куду 118
https://developer.nvidia.com/cuda-11-8-0-download-archive

### Установить зависимости Pytorch с CUDA
`pip install -r extensions/cuda/requirements.cuda.txt --index-url https://download.pytorch.org/whl/cu118`

### Установить расширение
`python extensions/cuda_extensions/setup.py install`



## Тестирование
`pytest tests/functional/`