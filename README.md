# Web-Fur-Player
Non-functional attempt at making a .fur (furnace tracker file) player for the web.

Only small .fur files work, and only after pausing with the browser's debugger and stepping through some commands.

When the program works, it will download a .wav file containing the contents of the .fur rendered to audio, and a text file containing all the logs sent to the console.

The file `gb-black-rainbows.fur` in this repository is an example of a .fur file that works with this player.

To build: get the Furnace tracker source, and compile it with this Emscripten command:
<code>
emcmake cmake .. -DBUILD_GUI=OFF -DUSE_RTMIDI=OFF -DUSE_SNDFILE=ON -DUSE_BACKWARD=ON -DUSE_SDL2=OFF -DWITH_PORTAUDIO=OFF -DWITH_RENDER_SDL=OFF -DWITH_RENDER_OPENGL=OFF -DWITH_RENDER_DX11=OFF -DUSE_FREETYPE=OFF -DWITH_DEMOS=OFF -DWITH_INSTRUMENTS=OFF -DWITH_WAVETABLES=OFF -DCMAKE_CXX_FLAGS="-O3 -pthread -sALLOW_BLOCKING_ON_MAIN_THREAD=1 -sEXPORTED_RUNTIME_METHODS=FS -s PTHREAD_POOL_SIZE_STRICT=0 -sMODULARIZE -s EXPORT_NAME=WebFurPlayer -sSTACK_SIZE=1048576 -Wno-unused-command-line-argument " -DCMAKE_C_FLAGS="-O3 -pthread -sALLOW_BLOCKING_ON_MAIN_THREAD=1 -sEXPORTED_RUNTIME_METHODS=FS -s PTHREAD_POOL_SIZE_STRICT=0 -sMODULARIZE -s EXPORT_NAME=WebFurPlayer -sSTACK_SIZE=1048576 -Wno-unused-command-line-argument "
</code>

Thanks to @gzuidhof for [coi-serviceworker](https://github.com/gzuidhof/coi-serviceworker/tree/master).
