<p><b>Referências</b></p>
<ul>
<li>https://medium.com/@jjlovesstudying/python-cuda-set-up-on-windows-10-for-gpu-support-78126284b085</li>
<li>https://www.youtube.com/watch?v=oRrKurk4pBU</li>
</ul>

<p><b>Testado com GTX 1660 e driver 460.89</b></p>

<p>Baixar Visual Studio 2017</p>
<ul><li>https://docs.microsoft.com/en-us/visualstudio/productinfo/vs2017-system-requirements-vs</li></ul>
<p>Download Community Button</p>
<p>arquivo = vs_community__633135658.1610317902</p>
<p>Na instalação selecionar apenas C++ conforme</p>
<p><b>Instalar CUDA 10.0</b></p>
<ul><li>https://developer.nvidia.com/cuda-10.0-download-archive</li></ul>
<p>cuda_10.0.130_411.31_win10.exe</p>
<p><b>Instalação personalizada: como o driver instalado é recente, desmarquei a opção de Drivers components e Other components</b></p>
<p>Após a instalação, adicionar CUDA_PATH e CUDA_PATH_V10_0 nas variáveis do ambiente</p>
<p>Buscar por environment</p>

<p><b>cuDNN 7.6.4</b></p>
<ul><li>https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.4.38/Production/10.0_20190923/cudnn-10.0-windows10-x64-v7.6.4.38.zip</li></ul>
<p>Janela 1: Abrir o arquivo .zip</p>
<p>Janela 2: C:\Users\ALAN\Downloads\cudnn-10.0-windows10-x64-v7.6.4.38.zip\cuda</p>

<p>Copiar o arquivo cudnn64_7.dll da pasta bin da Janela 1 para a pasta bin da Janela 2</p>
<p>Fazer o mesmo com o arquivo cudnn.h da pasta include</p>
<p>E com o arquivo cudnn.lib da pasta lib/x64</p>

<p><b>Anaconda</b></p>
<p>Instalar anaconda marcando a opção de adicionar nas variáveis do ambiente
<ul><li>https://www.anaconda.com/products/individual</li>
<li>https://repo.anaconda.com/archive/Anaconda3-2020.11-Windows-x86_64.exe</li></ul>
<p>5 novos caminhos foram adicionados referente ao programa Anaconda</p>

<p><b>Executar cmd como administrador</b></p>

```
conda create -n dl4cv
```

y e Enter

```
conda activate dl4cv
pip install python==3.6.9
pip install numpy
pip install tensorflow-gpu==2.0.0
pip install opencv-contrib-python
pip install scikit-image
pip install pillow
pip install imutils
pip install scikit-learn
pip install matplotlib
pip install progressbar2
pip install beautifulsoup4
pip install pandas
```

<p><b>Jupyter Notebook no ambiente virtual</b></p>
<p>Abrir Anaconda navigator</p>
<p>Em Home, escolhendo dl4cv no menu Application on, instalar Jupyter Notebook</p>
<ul><li>https://www.youtube.com/watch?v=otzZRZtXlOs</li></ul>
<p>Agora é possível importar as bibliotecas instaladas nele</p>

<p><b>TensorFlow Object Detection API</b></p>
<ul><li>https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html</li></ul>
<p>Em C:\Users\ALAN\Documents\TensorFlow
<p>Extrair https://github.com/tensorflow/models
<p>Renomear models-master para models</p>
<p>Baixar</p>
<ul><li>https://github.com/protocolbuffers/protobuf/releases/tag/v3.4.0</li>
</li>https://github.com/protocolbuffers/protobuf/releases/download/v3.4.0/protoc-3.4.0-win32.zip</li></ul>

<p>Extrair os arquivos e copiar o arquivo .exe da pasta bin para</p>
<p>C:\Users\ALAN\Documents\TensorFlow\models\research</p>

<p>Dentro do ambiente virtual dl4cv</p>

<p>cd C:\Users\ALAN\Documents\TensorFlow\models\research</p>
<p>Então executar</p>

```
protoc object_detection/protos/*.proto --python_out=.
```

```
pip install cython
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```

<p>Adicionar na variável do ambiente</p>
<p>C:\Users\ALAN\Documents\TensorFlow\models\research</p>
<p>C:\Users\ALAN\Documents\TensorFlow\models\research\object_detection</p>
<p>C:\Users\ALAN\Documents\TensorFlow\models\research\slim</p>

<p>Em um novo terminal de comando</p>

```
conda activate dl4cv
cd C:\Users\ALAN\Documents\TensorFlow\models\research
```

<p>Por fim (a versão da biblioteca TensorFlow é mantida igual)</p>

```
python setup.py build
python setup.py install
```

<p>Testar em uma nova janela</p>

```
conda activate dl4cv
python
import object_detection
```

<p>Com isso é possível usar o Jupyter</p>
