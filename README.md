# Twitch-YTLikeTheaterMode

Bookmarklet to change Twitch to YouTube-like Theater Mode Layout

![How it works](./TwitchTheaterMode.gif)



## Bookmarklet

How to install:
1. Add website (something you like) as bookmark.
1. Open bookmark editor dialog for it.
1. Rename bookmark. (ex. Theater Mode)
1. Enter the following code as "URL" in bookmark editor dialog.
1. Done.

```javascript
javascript: {

  let sidebarEl = document.getElementById('sideNav');
  let sidebarWidthPx = sidebarEl.offsetWidth+'px';
  let offsetTopStyle = 'calc( (100vw - '+sidebarWidthPx+') * 0.5625 )';
  let transitionParam = ' 0.5s ease';

  let playerEl = document.getElementsByClassName('persistent-player tw-elevation-0')[0];
  playerEl.style.setProperty('width', '100%', 'important');
  playerEl.style.setProperty('transition', 'width'+transitionParam, 'important');

  let chatEl = document.getElementsByClassName('channel-root__right-column channel-root__right-column--expanded')[0];
  chatEl.style.setProperty('bottom', '0px', 'important');
  chatEl.style.setProperty('height', 'calc(100% - '+offsetTopStyle+')', 'important');
  chatEl.style.setProperty('transition', 'bottom'+transitionParam+', height'+transitionParam, 'important');

  let infoEl = document.getElementsByClassName('channel-root__info channel-root__info--with-chat')[0];
  infoEl.style.setProperty('margin-top', offsetTopStyle, 'important');
  infoEl.style.setProperty('transform', '', 'important');
  infoEl.style.setProperty('transition', 'margin-top'+transitionParam+', transform'+transitionParam, 'important');

  let buttonEl = document.getElementsByClassName('right-column__toggle-visibility toggle-visibility__right-column toggle-visibility__right-column--expanded tw-absolute tw-flex tw-flex-grow-0 tw-flex-shrink-0 tw-visible tw-z-above')[0];
  buttonEl.style.setProperty('top', 'calc(1rem + '+offsetTopStyle+')', 'important');
  buttonEl.style.setProperty('transition', 'top'+transitionParam, 'important');

}
```
