- ls - let you see the contents of the current directory (files and folders)
- cd - lets us change our current directory
    - cd demos - move us into the demos folder
    - cd .. - move us one layer "outwards"
    - cd ../projects - move us outside of demos into intro projects
- mkdir - create a new folder
    - mkdir pizza - makes a new directory called pizza
- touch - creates a new file, can have extensions (.txt, .java)
    - touch peperoni creates a new file called peperoni
- vim  - lets us edit the file
    - vim sauce.txt - lets us enter the vim menu for the file called sauce.txt
    - vim is a way for us to edit files
    - First, we can press i to enter insert mode (which means we can write text)
    - Enter some text
    - Hit escape to exit insert mode
    - To save the file, we type in :wq (write and quit), and hit enter
- cat - lets us view a file
    - cat sauce.txt - lets us view the contents of sauce.txt
- rm - delete a file or a folder
    - rm peperoni - remove the file called peperoni
    - rm -r pizza - delete the directory (we need the -r if we're deleting a directory)
- mv - move a file to a specified location
    - mv grass ../green - move the file "grass" out of the current directory and into the green directory
    - mv cat dog notes - move both files (cat and dog) into the folder notes
    - mv cat cat1 - rename cat to cat1, assuming cat1 doesn't already exist