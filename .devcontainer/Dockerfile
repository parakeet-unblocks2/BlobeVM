FROM mcr.microsoft.com/vscode/devcontainers/base:fedora
RUN sudo dnf install -y \
    @xfce-desktop-environment \
    tigervnc-server \
    xorg-x11-fonts-75dpi \
    xorg-x11-fonts-100dpi \
    xterm \
    dbus-x11 \
    sudo \
    && sudo dnf clean all
    ENV DISPLAY=:1
    EXPOSE 5901
    RUN echo "#!/bin/bash\nvncserver $DISPLAY -geometry 1280x1024 -depth 24" > /home/vscode/start-vnc.sh \
    && chmod +x /home/vscode/start-vnc.sh
    CMD ["/home/vscode/start-vnc.sh"]