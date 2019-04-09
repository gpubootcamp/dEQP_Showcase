# dEQP_Showcase
List all u known cases of dEQP => give it good explanation &amp; picture => Make it as good case dict

# Reference
https://github.com/KhronosGroup/VK-GL-CTS
https://github.com/KhronosGroup/VK-GL-CTS/blob/master/external/openglcts/README.md

# Build
cmake -DDEQP_TARGET=default(xxx_emu) -DGLCTS_GTF_TARGET=gles31 -G "Visual Studio 15"

- directly works
> D:\git\OES\VK-GL-CTS-2\VK-GL-CTS-master
>
> cmake -DDEQP_TARGET=default -G "Visual Studio 15 Win64"
>
> cmake -DDEQP_TARGET=default -G "Visual Studio 15"
>
> cmake --build .

- Relative path failed 
@openglcts\README.md Building GL, ES2 or ES3.x cts
> cmake <path to openglcts> -DDEQP_TARGET=default -G"<Generator Name>"
>  
> cmake D:\git\OES\VK-GL-CTS-master\external\openglcts\ -DDEQP_TARGET=default -DGLCTS_GTF_TARGET=gles31 -G "Visual Studio 15"
>
> make error: Not found PCH @146line => PCH macro define in VK-GL-CTS\CMakeList.txt
  
- Rebuild
> Remove CMakeFiles dir

> Delete CMakeCache.txt

# Run full CTS on Windows
cd external\openglcts\modulers
Release(Debug)\cts-runner.exe --type=es32

#Run individual test or group of CTS on Windows
cd external\openglcts\modulers
Debug\glcts.exe --deqp-gl-context-type=egl --deqp-case=KHR-GLES31.core...

