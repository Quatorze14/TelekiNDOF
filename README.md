# TelekiNDOF
TelekiNDOF - Blender addon to move object with a NDOF mouse (Windows only)
## Description
TelekiNDOF takes the advantage of a 3D mouse to move object inside of Blender. It uses the Pywinusb library and the spacenavigator project (the later available on GitHub : [johnhw/pyspacenavigator](https://github.com/johnhw/pyspacenavigator)). The pywinusb is the reason for which the addon only works on windows machine. The addon will appear in the property panel. 

## Tutorial
I've made a Youtube tutorial to show how to use the addon. You can watch it there : [https://youtu.be/Zw79EofTLbs](https://youtu.be/Zw79EofTLbs). 

For a short introduction here is some of the things you can do with it:
1. Assign a shortcut.
2. Change the axis direction and axis sensitivity.
3. Use the Telekinesis button to control the active object.

Once activate the Telekinesis function act like the move command. You can then accept changes with left click and cancel with right click.  

## Older version of Blender
If you're using an older version of blender (before 2.93) you might encounter an error where it opens again and again. And an error that will look like 
```ModuleNotFoundError: No module named 'pywinusb'```

If this happen, I would recommand to update blender to a newer version. But if for some reasons you need the old version of blender and TelekiNDOF follow the next steps very carefully :
1. unzip the folder and open `__init__.py`
2. comment line 36 to 44 as follow (alternatively you can remove those lines):
```
#import subprocess
 
#py_exec = str(sys.executable)
# ensure pip is installed
#subprocess.call([py_exec, "-m", "ensurepip", "--user" ])
# update pip (not mandatory but highly recommended)
#subprocess.call([py_exec, "-m", "pip", "install", "--upgrade", "pip" ])
# install packages
#subprocess.call([py_exec,"-m", "pip", "install", f"--target={py_exec[:-14]}" + "lib", "pywinusb"])
```
3. rezip all the file to be able to install the addon. 
4. Open the command prompt and navigate to your blender python directory (usually 'C:\Program Files\Blender Foundation\Blender 2.83\2.83\python\bin') using the cd command. Make sure to adjust the command for your installation.
```
cd C:\Program Files\Blender Foundation\Blender 2.83\2.83\python\bin
```
5. Update pip using the following command : 
```
python.exe -m pip install --upgrade pip --user
```
6. Install pywinusb using this command : 
```
python.exe -m pip install pywinusb
```
7. Open Blender and install the rezip file as an addon.