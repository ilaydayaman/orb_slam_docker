## Setup Instructions

1. Download the Github repository

```console
git clone --recursive https://github.com/ilaydayaman/orb_slam_docker
```

2. Initialize submodules in the folder Girhub repository is downloaded

```console
git submodule update --init --recursive
```

3. Install [docker](https://docs.docker.com/engine/install/)

4. Install [nvidia container toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) (optional)

5. Build container - after making sure you have the previliges to run the code (chmod u+x ./build_docker.sh & chmod 744 ./build_docker.sh). The file on /thirdparty/makedeps.sh might need the same configuration. 

```console
./build_docker.sh
```
6. download [EuRoc dataset](http://robotics.ethz.ch/~asl-datasets/ijrr_euroc_mav_dataset/machine_hall/MH_01_easy/MH_01_easy.zip)

   unpack at /path/to/dataset_folder
   
7. open container in terminal

```console
./run_docker.sh /path/to/dataset_folder
```

8. run orbslam example code

```console
./Examples/Monocular-Inertial/mono_inertial_euroc ./Vocabulary/ORBvoc.txt ./Examples/Monocular-Inertial/EuRoC.yaml /data/MH_01_easy ./Examples/Monocular-Inertial/EuRoC_TimeStamps/MH01.txt
```
