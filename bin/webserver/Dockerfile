FROM wordpress:latest

# Install xdebug
RUN pecl install xdebug-2.8.0
RUN docker-php-ext-enable xdebug

# Prepare xdebug
RUN echo 'zend_extension="/usr/local/lib/php/extensions/no-debug-non-zts-20160303/xdebug.so"' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_enable=1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini

# Prepare xdebug
ARG XDEBUG_INI=/usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN echo "xdebug.default_enable = on" >> ${XDEBUG_INI} \
    && echo "xdebug.remote_enable = on" >> ${XDEBUG_INI} \
    && echo "xdebug.remote_autostart = on" >> ${XDEBUG_INI} \
    && echo "xdebug.remote_connect_back = on" >> ${XDEBUG_INI} \
    && echo "xdebug.remote_port = 9000" >> ${XDEBUG_INI}
# && echo "xdebug.remote_host = 192.168.11.6" >> ${XDEBUG_INI}

