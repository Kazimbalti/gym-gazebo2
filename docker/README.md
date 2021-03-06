# gym-gazebo2 Docker container usage

## Build the container

```shell
cd ~ && git clone https://github.com/AcutronicRobotics/gym-gazebo2
cd ~/gym-gazebo2/docker
docker build -t gg2 .
```

## Run the container

```shell
cd gym-gazebo2/docker
docker rm gg2 || true && docker run -it --name=gg2 -h gym-gazebo2 -v `pwd`:/tmp gg2
cp -r /root/ros2_mara_ws /tmp #Inside the docker container, used to load visual models
cd examples/MARA && python3 gg_random.py #Run the example
```

## Run the example
```shell
cd examples/MARA
python3 gg_random.py
```

### Launch gzclient (GUI)

Make sure you have gazebo already installed in your main Ubuntu system. If you are already running the simulation in the default port, you can access the visual interface the following way opening a new terminal:
```shell
# Do not use -g --gzclient flag
cd ~/gym-gazebo2/docker
sh gzclient.sh
```
