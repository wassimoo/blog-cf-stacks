FROM amazon/amazon-ecs-sample:latest

RUN echo "<?php \
    echo '<pre>'; \
    \$metadata_url = getenv('ECS_CONTAINER_METADATA_URI_V4'); \
    if (\$metadata_url) { \
        \$response = file_get_contents(\$metadata_url); \
        \$metadata = json_decode(\$response, true); \
        \$pretty_json = json_encode(\$metadata, JSON_PRETTY_PRINT); \
        echo \$pretty_json; \
    } else { \
        echo 'ECS_CONTAINER_METADATA_URI_V4 not set'; \
    } \
    echo '</pre>'; \
?>" > /var/www/html/index.php

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]
