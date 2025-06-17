FROM ubuntu :16.10
ENV DEBIAN FRONTEND = noninteractive
RUN sed -i - re ’s /([ a - z ]{2}\.) ? archive . ubuntu . com | security . ubuntu . com / old -
releases . ubuntu . com / g ’ / etc / apt / sources . list
RUN apt - get update & & \
apt - get install -y openssh - client iproute2 & & \
apt - get clean & & \
rm - rf / var / lib / apt / lists /*
CMD [ " tail " , " -f " , " / dev / null " ]
