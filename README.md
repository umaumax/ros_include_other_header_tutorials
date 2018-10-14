# ros_include_other_header_tutorials

## 他のパッケージのheaderを利用する
`find_package`に依存パッケージを追加
```
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  ros_header_tutorials
)
```

利用したい側のパッケージで適切に`INCLUDE_DIRS`が設定されていることが条件
```
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
  ${ros_header_tutorials_INCLUDE_DIRS}
)
```

設定されていない場合には簡易的に以下の場合でも可能
```
${ros_header_tutorials_SOURCE_DIR}/include
```

----

`package.xml`の記述については未調査
