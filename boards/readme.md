# 开发板配置  

这里提供一个Arduino UNO的做参考：
```json
{
    "name": "Arduino UNO",
    "version":"1.0.0",
    "description": "Arduino UNO standard compatible board",
    "compilerTool": "arduino-cli",
    "core": "arduino:avr@1.8.5",
    "type": "arduino:avr:uno",
    "compilerParam": "compile -v -b arduino:avr:uno",
    "uploadParam": "upload -v -b arduino:avr:uno -p ${serial}",
    "analogPins": [
        ["A0","A0"],["A1","A1"],["A2","A2"],["A3","A3"],["A4","A4"],["A5","A5"]
    ],
    "digitalPins": [
        ["0","0"],["1","1"],["2","2"],["3","3"],["4","4"],["5","5"],["6","6"],["7","7"],["8","8"],["9","9"],["10","10"],["11","11"],["12","12"],["13","13"],["A0","A0"],["A1","A1"],["A2","A2"],["A3","A3"],["A4","A4"],["A5","A5"]
    ],
    "pwmPins": [
        ["3","3"],["5","5"],["6","6"],["9","9"],["10","10"],["11","11"]
    ],
    "serialPort": [
        ["Serial","Serial"]
    ],
    "serialSpeed": [
        ["1200","1200"],["9600","9600"],["14400","14400"],["19200","19200"],["38400","38400"],["57600","57600"],["115200","115200"]
    ],
    "spi": [
        ["SPI","SPI"]
    ],
    "spiPins": {
        "SPI": [
            ["MOSI",11],["MISO",12],["SCK",13]
        ]
    },
    "spiClockDivide": [
        ["2 (8MHz)","SPI_CLOCK_DIV2"],["4 (4MHz)","SPI_CLOCK_DIV4"],["8 (2MHz)","SPI_CLOCK_DIV8"],["16 (1MHz)","SPI_CLOCK_DIV16"],["32 (500KHz)","SPI_CLOCK_DIV32"],["64 (250KHz)","SPI_CLOCK_DIV64"],["128 (125KHz)","SPI_CLOCK_DIV128"]
    ],
    "i2c": [
        ["I2C","Wire"]
    ],
    "i2cPins": {
        "Wire": [
            ["SDA","A4"],["SCL","A5"]
        ]
    },
    "i2cSpeed": [
        ["100kHz","100000L"],["400kHz","400000L"]
    ],
    "builtinLed": [
        ["BUILTIN_LED","13"]
    ],
    "interrupt": [
        ["interrupt0","2"],["interrupt1","3"]
    ]
}
```


### 编译上传配置：
```json
    "compilerTool": "arduino-cli",  // 使用的编译工具，目前都是arduino-cli，不需要更改
    "core": "arduino:avr@1.8.5",    // 开发板核心及对应版本号
    "type": "arduino:avr:uno",      // 开发板类型
    "compilerParam": "compile -v -b arduino:avr:uno",  //编译参数
    "uploadParam": "upload -v -b arduino:avr:uno -p ${serial}",  //上传参数，其中${serial}是串口变量，实际使用时会替换成用户选择的串口
```
这些配置，可见[arduino-cli文档](https://arduino.github.io/arduino-cli)  
你可能使用到的命令：
```bash
arduino-cli core list // 列出已安装的核心
arduino-cli board search // 列出可用的开发板
```

### 引脚等配置：
```json
"digitalPins": [
        ["0","0"],["1","1"],["2","2"],["3","3"],["4","4"],["5","5"],["6","6"],["7","7"],["8","8"],["9","9"],["10","10"],["11","11"],["12","12"],["13","13"],["A0","A0"],["A1","A1"],["A2","A2"],["A3","A3"],["A4","A4"],["A5","A5"]
    ]
```
这些配置是用于block调用的，如：
![](https://github.com/coloz/b4a-cloud/blob/master/doc/img/img1.jpg?raw=true)
