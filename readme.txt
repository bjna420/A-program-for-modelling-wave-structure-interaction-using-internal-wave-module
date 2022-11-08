KIOSTFOAM Installation manual

1. OpenFOAM installation
Please refer to OpenFOAM installation link below

os : ubuntu 14.04 기준
https://openfoam.org/download/2-4-0-ubuntu/
os : ubuntu 16.04 기준
https://openfoamwiki.net/index.php/Installation/Linux/OpenFOAM-2.4.0/Ubuntu#Ubuntu_16.04

2. Waves2FOAM 설치
Waves2FOAM 매뉴얼 (manualWaves2Foam_v090.pdf)의 Installation of Wave2FOAM 참고 (p10)
※ gfortran 설치 확인(설치 : sudo apt-get install gfortran)

2.1 Waves2FOAM required library installation
sudo apt-get install git
sudo apt-get install libgsl0-dev

2.2 Wave2FOAM installation
mkdir -p $FOAM_RUN/../applications/utilities
cd $FOAM_RUN/../applications/utilities
svn co http://svn.code.sf.net/p/openfoam-extend/svn/trunk/\
Breeder_1.6/other/waves2Foam
cd waves2Foam
./Allwmake

2.3 Check installation and execution status using the command below (<Figure 1>)
waveFoam -help
 
<Figure 1> waveFoam -help

3. KIOSTFOAM installation
3.1 Copy files below to /OpenFOAM/delft3d-2.4.0/applications/utilities/waves2Foam waves2FoamKIOST_V1.4.1.tar
- waves2FoamKIOST_V1.4.1_patch.tar
- waves2FoamKIOST_V1.4.1_cnoidal.tar

3.2 Unzip the file
tar xvf waves2FoamKIOST_V1.4.1.tar
tar xvf waves2FoamKIOST_V1.4.1_patch.tar
tar xvf waves2FoamKIOST_V1.4.1_cnoidal.tar

3.3 Copy files below to /OpenFOAM/delft3d-2.4.0/applications/utilities/waves2Foam/bin 
- bashrc
- bashrc.org

3.4 KIOSTFOAM installation
Go to /home/delft3d/OpenFOAM/delft3d-2.4.0/applications/utilities/waves2Foam and type command below
./Allwclean
./bin/install.add
./Allwmake

3.5 confirm execution using the command below (<Figure 2>)
waveIWMDyMFoam -help
 
< Figure 2> waveIWMDyMFoam -help


