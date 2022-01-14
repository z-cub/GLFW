![GLFW](media/glfw_logo.svg)  

[![Chat on Discord](https://img.shields.io/discord/754884471324672040.svg?logo=discord)](https://discord.gg/tPWjMwK) [![Twitter Follow](https://img.shields.io/twitter/follow/tinyBigGAMES?style=social)](https://twitter.com/tinyBigGAMES)
# GLFW
### Graphics Library Framework for OpenGL

Pascal bindings that allow you to use **GLFW** and other useful C libraries with <a href="https://www.embarcadero.com/es/products/delphi" target="_blank">Delphi</a>. 

### Included
- **GLFW** (https://github.com/glfw/glfw)
- **enet** (https://github.com/lsalzman/enet)
- **miniaudio** (https://github.com/mackron/miniaudio)
- **minizip** (https://github.com/madler/zlib)
- **physfs** (https://github.com/icculus/physfs)
- **pl_mpeg** (https://github.com/phoboslab/pl_mpeg)
- Nuklear (https://github.com/Immediate-Mode-UI/Nuklear)

### Minimum Requirements 
- Windows 10+ (64 bits)
- <a href="https://www.embarcadero.com/products/delphi/starter" target="_blank">Delphi Community Edition</a> (Win64 platform only)

### Usage
You simply add `GLFW` to your uses section and everything will be linked in your executable, ready for use with no DLLs to maintain. You will have direct access to all the aforementioned libraries.

```Pascal
uses
  System.SysUtils,
  GLFW,
  GLFW.Glad;
  
begin
  var Window: PGLFWwindow;

  // Initialize the library
  if glfwInit() = GLFW_FALSE then
    Exit;

  // Create a windowed mode window and its OpenGL context
  Window := glfwCreateWindow(640, 480, 'Hello World', nil, nil);
  if (Window = nil) then
  begin
    glfwTerminate;
    Exit;
  end;

  // Make the window's context current
  glfwMakeContextCurrent(Window);

  // Load OpenGL
  gladLoadGL(TLoadProc(glfwGetProcAddress));

  // Loop until the user closes the window
  while glfwWindowShouldClose(Window) = GLFW_FALSE do
  begin
    // Render here
    glClear(GL_COLOR_BUFFER_BIT);

    // Clear window
    glClearColor(1.0/30.0, 1.0/31.0, 1.0/30.0, 1.0/1.0);

    // Swap front and back buffers
    glfwSwapBuffers(Window);

    // Poll for and process events
    glfwPollEvents;
  end;

  glfwDestroyWindow(Window);

  glfwTerminate;
end.
```

### Support
- <a href="https://github.com/tinyBigGAMES/GLFW/issues" target="_blank">Issues</a>
- <a href="https://github.com/tinyBigGAMES/GLFW/projects/1" target="_blank">Issue Tracking</a>
- <a href="https://github.com/tinyBigGAMES/GLFW/discussions" target="_blank">Discussions</a>
- <a href="https://github.com/tinyBigGAMES/GLFW/wiki" target="_blank">Wiki</a>
- <a href="https://tinybiggames.com/contact/" target="_blank">Contact</a>
- <a href="https://www.glfw.org/" target="_blank">GLFWL website</a>
- <a href="https://www.youtube.com/results?search_query=GLFW&sp=CAI%253D" target="_blank">GLFW on YouTube</a>


<p align="center">
<img src="media/delphi.png" alt="Delphi">
</p>
<h5 align="center">

Made with :heart: in Delphi
</h5>