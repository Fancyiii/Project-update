# 05-06
The following arguments need to be added to `mpconfigport.h`

1. `extern const struct _mp_obj_module_t mymodule_module;`

2. `{ MP_OBJ_NEW_QSTR(MP_QSTR_mymodule), (mp_obj_t)&mymodule_module }, \` to `EXTRA_BUILTIN_MODULES` macro

## 1. No arguement needs to be added in to the `mpconfigport.h`  
#### mymodule does not show up in circuitpython REPL

  This is a function in `C:\Users\Fan Siyi\Desktop\circuitpython-main\py\objmodule.c` that loads built in modules.
  
  Considering whether this function replace everything that is added in `mpconfigport.h`

  ![image](https://user-images.githubusercontent.com/100907159/167077464-0d912490-701f-40c0-a4b0-9ce93555a37f.png)
  
## 2. Add in the argument in `mpconfigport.h`

1. Changing the format compatible with the format shown in the picture below ![image](https://user-images.githubusercontent.com/100907159/167078739-0b4a9ee3-cb09-4e23-bece-43ae526dcde8.png)
2. Does not change the format, just add in `1` and create a macro that can add `2` inside. 
  ![image](https://user-images.githubusercontent.com/100907159/167094682-e3991743-6d7f-48a9-81da-d3d5500a4dd1.png)
#### Result: Able to build circuitpython, but failed to have mymodule in circuitpython REPL
  ![image](https://user-images.githubusercontent.com/100907159/167094832-b82cde96-1c64-4276-8a50-1564e9da7ec6.png)

#### Other hint
see highlight ![image](https://user-images.githubusercontent.com/100907159/167088047-9393b52f-86f2-4822-93e3-49ab7124a524.png)

