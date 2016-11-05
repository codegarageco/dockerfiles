FROM library/mysql:5.7

MAINTAINER Faizal Zakaria

RUN echo "GRANT ALL PRIVILEGES ON * . * TO 'tidyhq';" | mysql -h mysql -ptidyhqisawesome
RUN mysql_tzinfo_to_sql /usr/share/zoneinfo | mysql mysql -u tidyhq -piknowthisisnotsecuretosavehere

