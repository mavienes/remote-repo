# readme

里面包含从无到有的安装vrpn库，到电脑与青瞳软件端电脑（vrpn发射端）进行连接。


# **1.安装vrpn库**（**humble下安装**）

sudo apt install ros-humble-vrpn-mocap
#依赖
rosdep install --from-paths src -y --ignore-src




## **2.创建工作空间**

mkdir -p ~/chingmu_ws/src  
cd ~/chingmu_ws/

## **3.拷贝程序代码，编译**
colcon build

## **4.刷新环境变量**

source install/setup.bash
## 5.**运行代码**

#192.168.10.159为青瞳电脑ip
ros2 launch vrpn_mocap  client.launch.yaml server:=192.168.10.159 port:=3883

## 6. **查看接收到的数据:**（opional）
ros2 topic list
**查看发送中**
ros2 topic echo /vrpn_mocap/MCAvatar/pose

# 7.**录制一段数据**（opional）
timeout 30s ros2 bag record -o ~/mocap_data_full --regex "/vrpn_mocap/MCAvatar/.*"


![just do it](file:////tmp/wps-ma/ksohtml/wpsFpbgaQ.png)



