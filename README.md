### build and install myLib
run this in 'myLib/build'
```sh
cmake .. && cmake --build . && cmake --install . --prefix .
```
### use myLib
run this in 'use_my_lib_in_another_project/build'
```sh
cmake .. -DCMAKE_INSTALL_PREFIX=../../myLib/build/  && cmake --build . 
```


