FROM rust as build 
WORKDIR /home 
COPY ./server server
WORKDIR /home/server
RUN cargo build --release

FROM alpine as deploy
WORKDIR /home
COPY --from=build /home/server/target/release/server /home/app
COPY ./run.sh /home/run.sh
RUN ls -la /home
ENTRYPOINT [ "/bin/sh", "/home/run.sh" ]
EXPOSE 80