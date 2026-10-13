# dlorg_firstname_lastname

dlorg keeps your Downloads folder tidy by sorting new files into category
folders. It runs in the background and organizes files based on their type.

## What it does
- Watches ~/Downloads in real time
- Moves new files into Documents, Images, Videos, Audio or Other
- Runs as a systemd user service
- Starts automatically on login

## Installation
1. Clone the project:
    git clone https://github.com/MMA000/dlorg_firstname_lastname.git
    
    cd dlorg_firstname_lastname

2. Make the script executable:
    chmod +x dlorg

3. Create a shortcut:
    ln -s "$(pwd)/dlorg" ~/.local/bin/dlorg

4. Install the service:
    cp dlorg.service ~/.config/systemd/user/

5. Enable and start:
    systemctl --user daemon-reload
    systemctl --user enable dlorg.service
    systemctl --user start dlorg.service

## Folder structure

dlorg creates these folders inside ~/Downloads and moves files based on
their extension or filename:

- Documents/
    -    pdf/        – PDF files
    -    docs/       – doc, docx, odt, xls, xlsx, ppt, pptx
    -    text/       – txt files
    -    project1/   – filenames containing "project1"
    -    project2/   – filenames containing "project2"
    -    project3/   – filenames containing "project3"

- Images/       – jpg, jpeg, png, gif, bmp, svg
- Videos/       – mp4, mkv, mov
- Audio/        – mp3, wav, ogg, flac
- Other/        – directories and uncategorized files

## Screenshots

### dlorg service status
![dlorg service status](dlorg%20status.png)

### Example of organized Downloads folder
![Downloads folder structure](example%20of%20folder%20structure%20of%20Downloads.png)




