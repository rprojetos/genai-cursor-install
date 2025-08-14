# Install Cursor AI editor on Ubuntu 24.04 

1. Use the Download button on www.cursor.com web site. It will download the `NAME.AppImage` file.

2. Copy the .AppImage file to your Applications directory

```bash
cd ~/Downloads
mkdir -p ~/Applications
mv NAME.AppImage ~/Applications/cursor.AppImage
```

3. Install libfuse2

```bash
sudo apt update
sudo apt install libfuse2
```

4. Make it an executable

```bash
chmod +x ~/Applications/cursor.AppImage
```

5. Run  

```bash
~/Applications/cursor.AppImage --no-sandbox
```

6. Add `cursor` shortcut

Add to `.bashrc` or `.zshrc`

```bash
alias cursor='~/Applications/cursor.AppImage --no-sandbox'
```

## Criando o atalho / desktop
> nano ~/.local/share/applications/cursor.desktop

```
[Desktop Entry]
Version=1.0
Name=Cursor AI
Comment=AI-powered code editor
Exec=/home/rprojetos/Applications/cursor.AppImage --no-sandbox %U
Icon=/home/rprojetos/Applications/cursor-icon.png
Terminal=false
Type=Application
Categories=Development;IDE;
StartupNotify=true
```

## Icone para o cursor ai
Um exemplo de icone pode ser adquirido em:

[https://icons8.com/icons/set/cursor-ai](https://icons8.com/icons/set/cursor-ai)

Baixe como .png

mova o icone para o diretorio da aplicação cursor ai
> mv ~/Downloads/cursor-icon.png ~/Applications/cursor-icon.png

## Garantir permissões e caminhos
> chmod +x /home/rprojetos/Applications/cursor.AppImage

> ls -l /home/rprojetos/Applications/cursor.AppImage

> ls -l /home/rprojetos/Applications/cursor-icon.png

> chmod +x ~/.local/share/applications/cursor.desktop

## Atualize o banco e recarregue o Shell:
> update-desktop-database ~/.local/share/applications

> killall -SIGUSR1 gnome-shell

Agora abra o “Show Apps” e procure por Cursor AI.

Se quiser fixar no dock, abra uma vez pelo Show Apps e clique com o direito > Fixar.


