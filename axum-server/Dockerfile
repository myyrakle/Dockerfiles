FROM rust
WORKDIR /home 
COPY . server
WORKDIR /home/server
RUN cargo build --release
RUN ls -la /home/server/target/release
RUN cp /home/server/target/release/app /home/app.bin
ENTRYPOINT [ "sh", "-c", "/home/app.bin" ]
EXPOSE 80