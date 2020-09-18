FROM gcc:latest
# it can be the version that you want

COPY . /usr/src/cpp_test
# copying all the files in this source to that path in the image.
# The image already has that path.
# you can test that this is true by pulling gcc and running
# docker run -it gcc, and seeing whatsup. If it doesn't exists it creates one
# you can also write: COPY main.cpp destination

WORKDIR /usr/src/cpp_test
# working dir, selfexpl

RUN g++ -o Test main.cpp 
# previous steps that you want to do

CMD [ "./Test" ]
# the command that you actually need to run