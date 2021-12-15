FROM ubuntu:latest
RUN apt update
RUN apt install -y build-essential wget
ENV DEBIAN_FRONTEND=nointeractive
ENV TZ=Europe/Madrid
RUN apt install -yq libsdl2-dev libsdl2-ttf-dev libsdl2-image-dev libsdl2-mixer-dev
RUN apt install -yq mingw-w64
RUN apt install -yq zip
RUN mkdir -p ~/sdl_win
RUN wget https://www.libsdl.org/release/SDL2-devel-2.0.18-mingw.tar.gz -P ~/sdl_win
RUN tar xf ~/sdl_win/SDL2-devel-2.0.18-mingw.tar.gz -C ~/sdl_win
RUN wget https://www.libsdl.org/projects/SDL_image/release/SDL2_image-devel-2.0.5-mingw.tar.gz -P ~/sdl_win
RUN tar xf ~/sdl_win/SDL2_image-devel-2.0.5-mingw.tar.gz -C ~/sdl_win
RUN wget https://www.libsdl.org/projects/SDL_ttf/release/SDL2_ttf-devel-2.0.15-mingw.tar.gz -P ~/sdl_win
RUN tar xf ~/sdl_win/SDL2_ttf-devel-2.0.15-mingw.tar.gz -C ~/sdl_win
RUN wget https://www.libsdl.org/projects/SDL_mixer/release/SDL2_mixer-devel-2.0.4-mingw.tar.gz -P ~/sdl_win
RUN tar xvf ~/sdl_win/SDL2_mixer-devel-2.0.4-mingw.tar.gz -C ~/sdl_win
RUN mkdir -p /src/sdl2
VOLUME ["/src/sdl2"]
WORKDIR /src/sdl2
CMD ["make", "game.zip"]