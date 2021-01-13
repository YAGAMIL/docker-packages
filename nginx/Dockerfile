FROM nginx
RUN rm -f /etc/localtime \
&& ln -sv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
&& echo "Asia/Shanghai" > /etc/timezone

ARG TZ="Asia/Shanghai"

ENV TZ ${TZ}

#RUN apk upgrade --update \
#    && apk add bash tzdata \
#    && ln -sf /usr/share/zoneinfo/${TZ} /etc/localtime \
#    && echo ${TZ} > /etc/timezone \
#    && rm -rf /var/cache/apk/*

#VOLUME /home/matcloud/matcloud-all/other/front-end/newWeb/ /usr/share/nginx/html
#COPY newWeb /usr/share/nginx/html
COPY default.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
