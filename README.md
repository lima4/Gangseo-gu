# Gangseo-gu

## 가상환경 설치 방법

* Cuda nn 설치를 위해서 기본 사양 확인하기

  * Window & GPU 정보 확인
  
    * 장치관리자 - 디스플레이 어댑터를 통해서 확인
      ![image1](https://user-images.githubusercontent.com/96859526/160506845-502f2e15-2d5c-44c3-90d5-b21e57ef7acb.png)
  
  * Window & GPU 정보에 맞춰서 Driver Download
    * [Driver Download](https://www.nvidia.co.kr/Download/index.aspx?lang=kr)
   
  * GPU Driver 설치 
    * 기본 설정으로 설치 후 확인하기
    * ```c
      nvidia-smi
      ```

    * ![Untitled1](https://user-images.githubusercontent.com/96859526/160507337-16755341-300e-4f80-9b80-a267112f9052.png)

  * CUDA 버전 11.4에 맞춰서 Toolkit 설치
     * [Toolkit Download](https://developer.nvidia.com/cuda-11-4-4-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local) 
     * 11.4~ 모든 버전이 가능하지만 11.44버전으로 설치. Window11로 업그레이드하고 설치 방법에 대해서는 차이가 있다. 
     * ![Untitled3](https://user-images.githubusercontent.com/96859526/160507897-e1bc7d2c-9331-4074-a9ec-271dc5dd9035.png)
  * cuDNN 설치
    * cuDNN 설치하기 위해서 Nvidia 가입하기
    
    * [Join Nvidia](https://developer.nvidia.com/cudnn)
    * Tensorflow-gpu와 호환되는 cuDNN 버전 확인하기
    * [Version](https://www.tensorflow.org/install/source_windows#tested_build_configurations)
    * Window11과 GPU에 맞는 cuDNN과 호환되는 Tensorflow-gpu가 없다. 
    
  * 기존 Window11 업데이트 이전인 Window10의 Driver, Toolkit, cuDNN 설치하기 
    * [Driver Download](https://www.nvidia.co.kr/Download/index.aspx?lang=kr)
    * [Toolkit Download](https://developer.nvidia.com/cuda-11.2.0-download-archive) 11.2
    * [cuDNN Download](https://developer.nvidia.com/rdp/cudnn-archive) 8.1.1
  
  * cuDNN 환경설정
    * cuDNN 받은 파일을 CUDA가 설치된 경로에 덮어쓰기
    
    * 환경변수 확인
      * 시스템 환경 변수 편집 - 환경변수 
      * ![image](https://user-images.githubusercontent.com/96859526/160509179-d0fddb83-0f21-417d-9f6c-95a768548881.png)
      * 시스템 변수 - CUDA_PATH 확인하기 
      * 사용자 변수 - PATH 확인하기 
        * 사용자 변수 PATH 편집
        * cuDNN에서 받은 파일의 Bin, include, lib 경로 추가하기
        * C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin
        * C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\include
        * C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\lib
  * 가상환경 생성
    * ```c
      conda create -n (가상환경 이름) python=3.7
      ```
 * ETC
   * tensorflow-gpu, jupyternotebook, ipykernel 
     * ```c
       activate (가상환경 이름)
       pip install tensorflow-gpu==2.6.0  cudnn과 호환되는 tensorflow-gpu찾아서 설치하기
       pip install keras
       pip install jupyter notebook
       pip install ipykernel
       python -m ipykernel install --user --name (가상환경 이름)
       ```
       
  * 최종 설치 확인
    * ```c
      from tensorflow.python.client import device_lib
      print(device_lib.list_local_devices())
      ```
* GeoPands 및 Folium 설치하기

  * GeoPands는 정해진 순서 및 버전에 맞춰서 꼭 진행을 해야 GeoPandas 설치시 Error가 발생하지 않는다.
    * [GeoPandas Install Document](https://geopandas.org/en/stable/getting_started/install.html)
    * 필수 패키지
      * numpy
      * pandas
      * shapely
      * fiona
      * pyproj
      
    * Python Version, OS에 따라서 Version을 다운로드 받기
      * EX) Python 3.7 = 파일 이름에 cp37이 들어간 파일 다운
      * [Shapely Download](https://www.lfd.uci.edu/~gohlke/pythonlibs/#shapely)
      * [GDAL Download](https://www.lfd.uci.edu/~gohlke/pythonlibs/#gdal)
      * [Fiona Download](https://www.lfd.uci.edu/~gohlke/pythonlibs/#fiona)
      * 가상환경 Activate하고 사용할 Directory에 다운로드 받은 파일 옮기기 
    * 가장 중요한점!!!!!!!
      * Geopandas 설치를 위해서 순서가 가장 중요하다 .
      
        * ```c
          pip install pyproj
          pip install Shapely-1.8.1.post1-cp37-cp37m-win_amd64.whl
          pip install GDAL-3.4.2-cp37-cp37m-win_amd64.whl
          pip install Fiona-1.8.21-cp37-cp37m-win_amd64.whl
          pip install geopandas 
          ```
