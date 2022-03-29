# Gangseo-gu

## 가상환경 설치 방법

* Cuda nn 설치를 위해서 기본 사양 확인하기

  * Window & GPU 정보 확인
  
    * 장치관리자 - 디스플레이 어댑터를 통해서 확인
      ![image1](https://user-images.githubusercontent.com/96859526/160506845-502f2e15-2d5c-44c3-90d5-b21e57ef7acb.png)
  
  * Window & GPU 정보에 맞춰서 Driver Download
    * [Driver Download] (https://www.nvidia.co.kr/Download/index.aspx?lang=kr)
   
  * GPU Driver 설치 
    * 기본 설정으로 설치 후 확인하기
    * ```c
      nvidia-smi
      ```

    * ![Untitled1](https://user-images.githubusercontent.com/96859526/160507337-16755341-300e-4f80-9b80-a267112f9052.png)

  * CUDA 버전 11.4에 맞춰서 Toolkit 설치하
     * [Toolkit Download] (https://developer.nvidia.com/cuda-11-4-4-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local) 
     * 11.4~ 모든 버전이 가능하지만 11.44버전으로 설치. Window11로 업그레이드하고 설치 방법에 대해서는 차이가 있다. 
     * ![Untitled3](https://user-images.githubusercontent.com/96859526/160507897-e1bc7d2c-9331-4074-a9ec-271dc5dd9035.png)
  * cuDNN 설치
    * cuDNN 설치하기 위해서 Nvidia 가입하기
    * 
    * [Join Nvidia] (https://developer.nvidia.com/cudnn)
