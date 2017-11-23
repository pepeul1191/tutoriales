/*
 * Your Stylesheet
 *
 * This stylesheet is loaded when Atom starts up and is reloaded automatically
 * when it is changed and saved.
 *
 * Add your own CSS or Less to fully customize Atom.
 * If you are unfamiliar with Less, you can read more about it here:
 * http://lesscss.org
 */


/*
 * Examples
 * (To see them, uncomment and save)
 */

// style the background color of the tree view
.tree-view {
  // background-color: whitesmoke;
  font-size: 11px
}

// style the background and foreground colors on the atom-text-editor-element itself
atom-text-editor {
  // color: white;
  // background-color: hsl(180, 24%, 12%);
}

// style UI elements inside atom-text-editor
atom-text-editor .cursor {
  // border-color: red;
}


.platformio-ide-terminal .xterm {
  background-color: #282C34;
  color: ;

  ::selection {
    background-color: ;
  }

  .terminal-cursor {
    background-color: ;
  }
}


li.file.entry.list-item, .list-tree li.list-nested-item > .list-item {
  line-height: 18px;
}

.theme-one-dark-ui .settings-view {
  font-size: 12px;
}

.theme-one-dark-ui,
.theme-one-light-ui {
  .tab-bar {
    font-size: 11px; // smaller font size
  }
  .tab {
    min-width: 10em; // larger minimum width
    max-width: 16em; // smaller max width
  }
}
