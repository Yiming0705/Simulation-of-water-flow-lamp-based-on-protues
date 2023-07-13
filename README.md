# Simulation-of-water-flow-lamp-based-on-protues
通过对流水灯的仿真实现对protues的初步了解与使用
下面这个程序可以通过GPIO控制LED灯的亮灭，来模拟流水灯的效果：

#include <iostream>
#include <unistd.h>
#include <wiringPi.h>

#define LED_PIN 0

int main() {
    wiringPiSetup();
    pinMode(LED_PIN, OUTPUT);
    
    while (true) {
        digitalWrite(LED_PIN, HIGH);
        usleep(500000);  // 500ms延迟
        digitalWrite(LED_PIN, LOW);
        usleep(500000);  // 500ms延迟
    }
    
    return 0;
}
这个示例代码使用了wiringPi库来控制GPIO，并通过GPIO 0控制LED灯的亮灭。程序会循环地将LED灯点亮和熄灭，并在两次操作之间延迟500ms。
接下来，你需要在Proteus中创建一个仿真环境来测试你的代码。你可以使用Proteus提供的电路元件来模拟LED灯和GPIO接口。以下是一个简单的步骤：
打开Proteus软件，并创建一个新的工程。
在工程中添加一个Arduino元件，并连接一个LED灯到相应的引脚。
在Proteus中添加一个Virtual Terminal元件，用于显示程序的输出。
在Proteus中添加一个GPIO模拟器元件，并将其连接到Arduino的GPIO引脚。
将你的代码编译为可执行文件，并将其添加到Proteus中的Arduino元件。
运行仿真，观察LED灯是否按照预期的流水灯效果闪烁。
