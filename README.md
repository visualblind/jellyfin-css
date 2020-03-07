# jellyfin-css
Original creator /u/EdgeMentality 
See:
https://www.reddit.com/r/jellyfin/comments/bvnt65/sharing_even_more_custom_css_and_some_fixes_to/

Installation:
add this to the custom css section

```
@import url('https://raw.githubusercontent.com/visualblind/jellyfin-css/master/jf.css');
```

# Quote:

I posted some customizations to the web UI using the custom CSS field. You can find that post here.
I am posting all the same stuff here, below the new stuff, so check them for some new fixes.

To use these simply copypaste them into "Custom CSS" field in general settings. Modify or mix and match them as you like.

Darken the background
This darkens the background on blue radiance, edit the percentage depending how dark you want it. Higher is darker.

```
/* Darken background, only works with blue radiance*/
.backgroundContainer.withBackdrop {background-color: #000000; filter: brightness(50%);}
```

Make top menu transparent
Self explanatory

```
/*Top menu transparency*/
.skinHeader.skinHeader-withBackground.headroom.noHomeButtonHeader {background:none; background-color:rgba(0, 0, 0, 0);}
.skinHeader.skinHeader-withBackground.headroom {background:none; background-color:rgba(0, 0, 0, 0);}
```

Enlarge tab buttons
Enlarges the tab buttons, suggested, genres, etc. By default they are really damn tiny, especially on mobile.

```
/*Adjust both "size-adjust" and "size" to modify size*/
.headerTabs.sectionTabs {text-size-adjust: 100%;  font-size: 100%;}
```

These above three enabled look like this: 
![alt text](https://i.imgur.com/L7kG3No.jpg)

Minimalistic login page
This looks even better together with the transparent top menu. I also changed the width unit from my last post because it caused things to jump around on mobile. You can use the "hide user" for each user to get rid of the user profiles (I did not want them visible for everyone to know).

```
/*Narrow the login form*/
#loginPage .readOnlyContent, #loginPage form {max-width: 22em;}

/*Hide "please login" text, margin is to prevent login form moving too far up*/
#loginPage h1 {display: none}
#loginPage .padded-left.padded-right.padded-bottom-page {margin-top: 50px}

/*Hide "manual" and "forgot" buttons*/
#loginPage .raised.cancel.block.btnManual.emby-button {display: none}
#loginPage .raised.cancel.block.btnForgotPassword.emby-button {display: none}
```

End result:
![alt text](https://i.imgur.com/BrZxJh2.jpg)

Stylized episode previews
I have a 1440p monitor and as the episode previews are sized based on horizontal resolution, I ended up with a lot of wasted space on the episode summary and a high vertical page requiring a lot of scrolling to browse. My solution is maybe a little too simple but works very well and looks really cool in my opinion.

```
/*Size episode preview images in a more compact way*/
.listItemImage.listItemImage-large.itemAction.lazy {height: 110px;}
```

Looks like this in 1440p: ![alt text](https://i.imgur.com/tJNzOv3.jpg)

1080p: https://i.imgur.com/waY2Pix.jpg
Mobile: https://i.imgur.com/3xcYxl2.png

Stylized and shrunk cast info
Now with fixed default images. Before this did not round the default image displayed for actors who did not have images. I wasn't too fond of each actor taking up as much space as a season, so I changed it. Ended up very similar to how plex does it.

```
/*Shrink cast thumnails, you can use just this part if you only want them smaller*/
#castContent .card.portraitCard.personCard.card-hoverable.card-nofocustransform.card-withuserdata {width: 3.7cm; font-size: 80% !important;}
#castContent .card.portraitCard.personCard.card-nofocustransform.card-withuserdata {width: 3.7cm; font-size: 80% !important;}
#castContent .card.overflowPortraitCard.personCard.card-nofocustransform.card-withuserdata {width: 3.7cm; font-size: 80% !important;}

/*Correct image aspect ratio behaviour, set border-radius to zero for square tiles*/
#castContent .cardContent-button.cardImageContainer.coveredImage.cardContent.cardContent-shadow.itemAction.lazy {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardContent-button.cardImageContainer.coveredImage.defaultCardBackground.defaultCardBackground1.cardContent.cardContent-shadow.itemAction {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardContent-button.cardImageContainer.coveredImage.defaultCardBackground.defaultCardBackground2.cardContent.cardContent-shadow.itemAction {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardContent-button.cardImageContainer.coveredImage.defaultCardBackground.defaultCardBackground3.cardContent.cardContent-shadow.itemAction {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardContent-button.cardImageContainer.coveredImage.defaultCardBackground.defaultCardBackground4.cardContent.cardContent-shadow.itemAction {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardContent-button.cardImageContainer.coveredImage.defaultCardBackground.defaultCardBackground5.cardContent.cardContent-shadow.itemAction {background-size: cover; !important; border-radius: 1.7cm;}
#castContent .cardScalable {width: 3.1cm !important; height: 3.1cm !important; border-radius: 1.7cm;}
#castContent .cardOverlayContainer.itemAction {border-radius: 1.7cm;}

/*Center the mouseover favorites and threedot menu*/
#castContent .cardOverlayButton-br {bottom: 4%; right: 15%; width: 70%;}
#castContent .cardOverlayButton.cardOverlayButton-hover.itemAction.paper-icon-button-light {width: 50%; vertical-align: middle;}
#castContent .cardOverlayButton.cardOverlayButton-hover.itemAction.emby-button {width: 50%; vertical-align: middle;}
```
End result: ![alt text](https://i.imgur.com/DXlt1I2.jpg)
