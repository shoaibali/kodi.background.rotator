# kodi.background.rotator
A python script I hacked together to help me rotate wallpaper / background / art whatever the hell you want to call it! Due to limitation in Kodi allowing only 1 background image at a time.

# why this script?

I spent hours looking for such a simple addon that would just let me rotate background images on home screen from a given folder. I was very certain that such a addon must exist. I even went as far as looking in to code on how other addons set the Artwork, but no luck! Please feel free to let me know if such addon even exists or am I just did not looked hard enough. Maybe there are some skins that do allow this functionality, I prefer to stick to my simple 7-icon confluence skin.


# limitation in kodi

Kodi or the skin has a limitation under settings where you can only define an image as custom background. You cannot select the entire directory or sets of images. From what I learned you can set section sepcific Art also known as fan art.

![kodi custom background setting](https://raw.githubusercontent.com/shoaibali/kodi.background.rotator/master/screenshot.png?raw=true "Kodi custom background setting")

# how does this work

[The python script](randombackground.py) can be set to run in cronjob to randomly pick a file from directory in this case (/storage/pictures/)

```
rfilename=random.choice(os.listdir("/storage/pictures"))
```

Once it has picked a random file, it will rename it to be 'random.jpg'. However, before it renames it to random.jpg; it needs to rename the existing random.jpg to something random

```
	newname=picturespath + str(random.random()).rsplit('.',1)[1] + extension
```

# limitations of this script

* I would like to see this (concept) turn in to a proper Kodi addon (if it does not exist) already. 
* The path to location is hard coded /storage/pictures/ (this can be a dropbox to keep photos in sync from phones etc)
* Kodi will only look for '.jpg' format images. I will try and point it to a formatless (i.e without extension) or experiement with symlink




