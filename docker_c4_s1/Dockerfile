FROM ubuntu :22.10
ENV DEBIAN FRONTEND = noninteractive
RUN sed -i - re ’s /([ a - z ]{2}\.) ? archive . ubuntu . com | security . ubuntu . com / old -
releases . ubuntu . com / g ’ / etc / apt / sources . list
RUN apt - get update & & \
apt - get install -y openssh - client openssh - server sudo iproute2 & & \
apt - get clean & & \
rm - rf / var / lib / apt / lists /*
RUN useradd -m -s / bin / bash prueba & & \
echo " prueba : prueba " | chpasswd & & \
adduser prueba sudo
RUN mkdir -p / var / run / sshd
RUN sed -i ’s /# PermitRootLogin prohibit - password / PermitRootLogin yes / ’ /
etc / ssh / sshd config & & \
sed -i ’s /# PasswordAuthentication yes / PasswordAuthentication yes / ’ /
etc / ssh / sshd config & & \
sed -i ’s / PasswordAuthentication no / PasswordAuthentication yes / ’ / etc /
ssh / sshd config
RUN ssh - keygen -A
EXPOSE 22
CMD [ " / usr / sbin / sshd " , " -D " ]
