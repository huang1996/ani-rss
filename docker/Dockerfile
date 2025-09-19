FROM wushuo894/openj9:open-24-jre

COPY docker/run.sh /run.sh
COPY docker/exec.sh /exec.sh

COPY target/ani-rss-jar-with-dependencies.jar /usr/app/ani-rss-jar-with-dependencies.jar
WORKDIR /usr/app
VOLUME /config
VOLUME /vol1/1000/媒体
ENV PUID=0 PGID=0 UMASK=022
ENV PORT=7789 CONFIG=/config TZ=Asia/Shanghai
EXPOSE $PORT
RUN chmod +x /exec.sh /run.sh
# RUN test -f /exec.sh || echo "Error: exec.sh missing!" && exit 1
# CMD ["java","-Xms60m -Xmx1g -Xss256k -Xgcpolicy:gencon -Xquickstart -Xcompressedrefs -Xtune:virtualized -XX:+UseStringDeduplication -XX:-ShrinkHeapInSteps -XX:TieredStopAtLevel=1 -XX:+IgnoreUnrecognizedVMOptions --add-opens=java.base/java.net=ALL-UNNAMED --add-opens=java.base/sun.net.www.protocol.https=ALL-UNNAMED", "-jar", "/usr/app/ani-rss-jar-with-dependencies.jar","--port", "${PORT}"]
CMD ["java","-Xms60m -Xmx1g -Xss256k -Xgcpolicy:gencon -Xquickstart -Xcompressedrefs -Xtune:virtualized -XX:+UseStringDeduplication -XX:-ShrinkHeapInSteps -XX:TieredStopAtLevel=1 -XX:+IgnoreUnrecognizedVMOptions","-jar", "/usr/app/ani-rss-jar-with-dependencies.jar","--port", "${PORT}"]
