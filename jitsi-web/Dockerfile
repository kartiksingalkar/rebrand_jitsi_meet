FROM jitsi/web:${JITSI_IMAGE_VERSION:-stable-8319}


COPY --chown=root:root overrides /usr/share/jitsi-meet/
COPY --chown=root:root config/custom-interface_config.js /defaults/interface_config.js


# RUN sed -i "s|\(// \)\?defaultLanguage:.*|defaultLanguage: 'nl',|" /defaults/config.js; \
#     sed -e 's/welcome-background.png/welcome-background.jpg/' \
#     -e 's|.deep-linking-mobile .header{width:100%;height:70px;background-color:#f1f2f5;text-align:center}|.deep-linking-mobile .header{width:100%;height:70px;background-color:#003867;text-align:center}|' \
#     -e 's|.deep-linking-mobile .header .logo{margin-top:15px;margin-left:auto;margin-right:auto;height:40px}|.deep-linking-mobile .header .logo{margin-top:10px;margin-left:auto;margin-right:auto;height:50px}|' \
#     -i /usr/share/jitsi-meet/css/all.css; \
RUN    sed -e 's|"headerTitle": "Jitsi Meet"|"headerTitle": "Flex Meet"|' \
    -e 's|"headerSubtitle": .*|"headerSubtitle": "Secure and high quality meetings"|' \
    -i /usr/share/jitsi-meet/lang/main-enGB.json; \
    \
    sed -e 's|C().createElement("h1",{className:"header-text-title"},t("welcomepage.headerTitle"))|C().createElement("h1",{className:"header-text-title"},C().createElement("img",{src:"images/logo-deep-linking.png",alt:"Flex Meet",height:100}))|' \
    -e 's|"headerTitle":"Jitsi Meet"|"headerTitle":"Flex Meet"|' \
    -e 's|"headerSubtitle":"Secure and high quality meetings"|"headerSubtitle":"Secure and high quality meetings"|' \
    -i /usr/share/jitsi-meet/libs/app.bundle.min.js;
