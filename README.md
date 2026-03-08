# spintext.js

The web version of the spintext.c code. This code is heavily inspired by the donut.c spinning code, but focuses on spinning text as opposed to a donut. The web version preserves the majority of the functionality, but loses terminal based formatting (ie. colours beyond single colour, bold/faint text, etc.).

## A public web version is available on my website @ [spintext.joshuazc.com/?params](https://spintext.joshuazc.com)

The WASM and JS code are compiled directly from the slightly modified spintext.c code using Emscripten with the following flags:
`-sASYNCIFY -sEXPORTED_RUNTIME_METHODS=ccall -sFORCE_FILESYSTEM`

![image of spinning text](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExY242YjlzOTlzeTgzMWdrc2plY3VqZXZzajAwbmRyNHNvMHFhbWh4OCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/1LI3ZLDnyFnadsIXPQ/giphy.gif).

You can modify the params within your web browser with the `?params=(str)TEXT-(float)TILT-(float)SPIN-(float)ROLL-(float)PACE-(float)CAM_DIST` tags.  
All calculations are done on the clientside, this code has **not** been tested on many devices for optimization.  
The functionality has been confirmed on MacOS, iOS and Windows 11.  

I would absolutely **NOT** put this into another webpage with other things going on, or at the very least I would decrease the width/height and increase the delay between the rendering of frames (`emscripten_sleep(25)` is the default). It is VERY heavy compared to other browser applications.

