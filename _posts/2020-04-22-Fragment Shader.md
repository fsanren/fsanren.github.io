---
layout:     post
title:      Fragment Shader
subtitle:   
date:       2020-04-22
author:     fsanren
header-img: img/lyx-h-05.jpg
catalog: true
tags:
    - GLSL
    - openGL
---

## What is GLSL

GLSL stands for openGL Shading Language, which is the specific standard of shader programs

``` GLSL
#ifdef GL_ES
precision mediump float;
#endif

uniform vec2 u_resolution;
uniform vec2 u_mouse;
uniform float u_time;

void main() {
    vec2 st = gl_FragCoord.xy/u_resolution.xy;
    st.x *= u_resolution.x/u_resolution.y;

    vec3 color = vec3(0.);
    color = vec3(st.x,st.y,abs(sin(u_time)));

    gl_FragColor = vec4(color,1.0);
}
```

1. Shader Language has a single main function that returns a color at the end. This is similar to C.

2. The final pixel color is assigned to the reserved global variable gl_FragColor.

3. This language has built in variables (like gl_FragColor), functions and types.

4. vec4 four arguments respond to the RED, GREEN, BLUE and ALPHA channels. Also we can see that these values are normalized, which go from 0.0 to 1.0.

5. Another important C feature we can see in this example is the presence of preprocessor macros. Macros are part of a pre-compilation step. With them it is possible to #define global variables and do some basic conditional operation (with #ifdef and #endif). All the macro comands begin with a hashtag (#). Pre-compilation happens right before compiling and copies all the calls to #defines and check #ifdef (is defined) and #ifndef (is not defined) conditionals. In our "hello world!" example above, we only insert the line 2 if GL_ES is defined, which mostly happens when the code is compiled on mobile devices and browsers.

6. Float types are vital in shaders, so the level of precision is crucial. Lower precision means faster rendering, but at the cost of quality. You can be picky and specify the precision of each variable that uses floating point. In the first line (precision mediump float;) we are setting all floats to medium precision. But we can choose to set them to low (precision lowp float;) or high (precision highp float;).

The GPU has hardware accelerated angle, trigonometric and exponential functions. Some of those functions are:

 sin(), cos(), tan(), asin(), acos(), atan(), pow(), exp(), log(), sqrt(), abs(), sign(), floor(), ceil(), fract(), mod(), min(), max() and clamp().

### Uniforms

Because of the architecture of the graphics card those inputs are going to be equal (uniform) to all the threads and necessarily set as read only. In other words, each thread receives the same data which it can read but cannot change.

These inputs are called uniform and come in most of the supported types: float, vec2, vec3, vec4, mat2, mat3, mat4, sampler2D and samplerCube.

 Uniforms are defined with the corresponding type at the top of the shader right after assigning the default floating point precision.

### default variable

 GLSL gives us a default output, vec4 gl_FragColor, it also gives us a default input, vec4 gl_FragCoord.
