# Tag Core
It contains everything you need to know about the methods and calls in the tag class. In fact, this class is very powerful and multifunctional, as well as easily expandable. I will try to bring you up to date.

# Methods static
In fact, there are a lot of methods, it lists the standardly available methods that you can naturally override as well as extend to your own taste.

## resetCollect
`public static`: Reset collection.
```php
$tag->resetCollect();
```

## selector
`public static`: Almost `CSS` selector, works for the helper [_s](/TagCore/Helpers?id=_s)
```php
/**
 * @param string $selector
 * @return Collection|Tag|FindCollection
 * @throws \Exception
 */
$tag->selector(string $selector);
```

## addName
`public static`: Add a tag to the collection with your name.
```php
/**
 * @param string $name
 * @param Tag $tag
 */
$tag->addName(string $name, \Lar\Tagable\Tag $tag);
```

## cover
`public static`: Static alias from method when.
```php
/**
 * @return Tag
 */
$tag->cover();
```

## registerComponent
`public static`: Registration component.
```php
/**
 * @param string $name
 * @param \Closure|string $component
 * @throws \Exception
 */
$tag->registerComponent(string $name, $component);
```

## hasComponent
`public static`: Check if item exists or not.
```php
/**
 * @param string $name
 * @return bool
 */
$tag->hasComponent(string $name);
```

## injectFile
`public static`: Inject collection from file.
```php
/**
 * @param $file
 * @throws \Exception
 */
$tag->injectFile($file);
```

## injectCollection
`public static`: Inject collection in to component collection.
```php
/**
 * @param array $collection
 */
$tag->injectCollection($collection = []);
```

## getComponent
`public static`: Component getter.
```php
/**
 * @param string $name
 * @return mixed
 * @throws \Exception
 */
$tag->getComponent(string $name);
```

## create
`public static`: Static element create.
```php
/**
 * @throws \Exception
 * @return Tag
 */
$tag->create();
```

# Methods public

## view 
Insert blade view

## hide
`public`: Add to tag `style="display: none;"`.
```php
/**  
 * @param bool $eq You can pass a boolean value as a switch when rendering.
 * @return $this  
 */
$tag->hide($eq = true);
```

## haveAndGetSelector
`public`: Get the identifier attribute if there is, if not, create a unique attribute and return the `JS Query` selector.
```php
/**  
 * @return string  
 * @throws \Exception  
 */
$tag->haveAndGetSelector();
```

## haveAndGetSelectorID
`public`: Get the value of the identifier attribute if there is one, if not create a unique one and return the `JS Query` selector.
```php
/**  
 * @return string  
 * @throws \Exception  
 */
$tag->haveAndGetSelectorID();
```

## getSelector
`public`: Selector getter. Alias `haveAndGetSelectorID`
```php
/**
 * @return string
 * @throws \Exception
 */
$tag->getSelector();
```

## setUID
`public`: Set unique default tag attribute ID.
```php
/**
 * @return $this
 * @throws \Exception
 */
$tag->setUID();
```

## hasParent
`public`: Check if there is a parent object.
```php
/**  
 * @return bool  
 */
 $tag->hasParent();
```

## name
`public`: Set the internal name for easy access through the `_s` helper.
```php
/**  
 * @param string $name  
 * @return $this  
 */
$tag->name(string $name);
...
_s($name)->text("Hello");
```

## getObjName
`public`: Component name getter.
```php
/**
 * @return string
 */
$tag->getObjName();
```

## initTag
`public`: Tag initialize.
```php
/**
 * @param $element
 * @return Tag
 * @throws \Exception
 */
$tag->initTag($element);
```

## getElement
`public`: Element getter.
```php
/**
 * @return string
 */
$tag->getElement();
```

## isElement
`public`: Checks if an item has an element.
```php
/**
 * @return bool
 */
$tag->isElement();
```

## getParent
`public`: Parent getter.
```php
/**
 * @return Tag
 */
$tag->getParent();
```


## root
`public`: Root wrapper.
```php
/**
 * @param \Closure $closure
 * @return Tag
 */
$tag->root(\Closure $closure);
```

> Returns himself and not the parent.

## getRoot
`public`: Get the very first parent.
```php
/**
 * @return Tag
 */
$tag->getRoot();
```

## isTsElement
`public`: If the element of this tag is equal to the specified.
```php
/**
 * @param string $element
 * @return bool
 */
$tag->isTsElement(string $element);
```

## isClosingTag
`public`: Check if this tag closes or not.
```php
/**
 * @return bool
 */
$tag->isClosingTag();
```

## isDebug
`public`: Is debug mode.
```php
/**
 * @return bool
 */
$tag->isDebug();
```

## isRendered
`public`: Is rendered element.
```php
/**
 * @return bool
 */
$tag->isRendered();
```

## unRender
`public`: Clear render state.
```php
/**
 * @return $this
 */
$tag->unRender();
```

## unHash
`public`: Remove hash by name.
```php
/**
 * @param string $hash_name
 * @return $this
 */
$tag->unHash($hash_name = "RENDERED");
```

## setDebug
`public`: Debug mode setter.
```php
/**
 * @return Tag
 */
$tag->setDebug();
```

## getChildElementCount
`public`: Get child element count.
```php
/**
 * @return int
 */
$tag->getChildElementCount();
```

## setChildElementCount
`public`: Child element count setter.
```php
/**
 * @param int $child_element_count
 * @return Tag
 */
$tag->setChildElementCount(int $child_element_count);
```

## setParent
`public`: Parent setter.
```php
/**
 * @param Tag $tag
 * @return Tag
 */
$tag->setParent(\Lar\Tagable\Tag $tag);
```



## getRendered
`public`: Get render data.
```php
/**
 * @return string
 */
$tag->getRendered();
```

## setDatas
`public`: Set the values of the attribute "data-*".
```php
/**
 * @param array $datas
 * @return Tag
 * @throws \Exception
 */
$tag->setDatas(array $datas);
```
### Example 
```php
echo DIV::when("Click")->setDatas([
	"target" => "modal"
])->render();
```
Result
```html
<div data-target="modal">Click</div>
```

## hasClass
`public`: Check if the component has such a class.
```php
/**
 * .
 * @param string $class
 * @return bool
 */
$tag->hasClass(string $class);
```

## hasAttribute
`public`: Check whether the component has such an attribute.
```php
/**
 * .
 * @param string $attribute
 * @return mixed
 */
$tag->hasAttribute(string $attribute);
```

## getAttribute
`public`: Get attribute value.
```php
/**
 * @param string $attribute
 * @return string|array|bool
 */
$tag->getAttribute(string $attribute);
```

## removeAttribute
`public`: Remove attribute.
```php
/**
 * @param string|array $name
 * @return $this
 */
$tag->removeAttribute($name);
```

## attr
`public`: Attribute setter.
```php
/**
 * @param $name
 * @param null $value
 * @return $this
 * @throws \Exception
 */
$tag->attr($name, $value = "");
```

## text
`public`: Content setter.
```php
/**
 * @param $value
 * @param array $values
 * @return mixed
 * @throws \Exception
 */
$tag->text($value, ...$values);
```
## addClass
`public`: Add CSS class in to tag.
```php
/**
 * @param string|array $class
 * @return $this
 * @throws \Exception
 */
$tag->addClass(...$class);
```

## addClassIf
`public`:  Add CSS class in to tag if `$eq == true`
```php
/**
 * @param $eq
 * @param string|array $class
 * @return $this
 * @throws \Exception
 */
$tag->addClassIf($eq, ...$class);
```

## appEnd
`public`: Content append setter.
```php
/**
 * @param array $data
 * @return Tag
 * @throws \Exception
 */
$tag->appEnd(...$data);
```

## appEndIf
`public`: App end data if `$eq == true`
```php
/**
 * ...
 * @param $eq
 * @param mixed ...$data
 * @return $this
 * @throws \Exception
 */
$tag->appEndIf($eq, ...$data);
```

## _
`public`: Parent link.
```php
$tag->_();
```

## prepEnd
`public`: Content prepend setter.
```php
/**
 * @param array $data
 * @return Tag
 * @throws \Exception
 */
$tag->prepEnd(...$data);
```

## prepEndIf
`public`: Prep end data if.
```php
/**
 * ...
 * @param $eq
 * @param mixed ...$data
 * @return $this
 * @throws \Exception
 */
$tag->prepEndIf($eq, ...$data);
```

## content
`public`: Clear content and adds data if that to need.
```php
/**
 * .
 * @param array|string|\Closure $value
 * @return $this
 * @throws \Exception
 */
$tag->content(...$value);
```

## resetAttributes
`public`: Reset all attributes.
```php
/**
 * @return $this
 */
$tag->resetAttributes();
```

## anchor
`public`: Set anchor. `href="#anchor_name"`
```php
/**
 * @param string $name
 * @return $this
 */
$tag->anchor(string $name = "");
```

## clear
`public`: Clean component.
```php
/**
 * @throws \Exception
 */
$tag->clear();
```

## add
`public`: Add new child.
```php
/**
 * @param string $element
 * @param array $arguments
 * @return $this
 * @throws \Exception
 */
$tag->add(string $element, array $arguments = []);
```
## repeat
`public`: Paste this component into parent N times. Return parent.
```php
/**
 * @param int $time
 * @return $this
 */
$tag->repeat(int $time);
```

## when
`public|static`: When element.
```php
/**
 * @param $arguments
 * @return Helpers
 * @throws \Exception
 */
$tag->when(...$arguments);
```
## createUniqueAttribute
`public`: Create unique attribute from tag.
```php
/**
 * @return Helpers
 * @throws \Exception
 */
$tag->createUniqueAttribute();
```

## getUnique
`public`: Get unique identifier.
```php
/**
 * @return string
 */
$tag->getUnique();
```
## createUnique
`public`: Create unique inner identifier from tag.
```php
/**
 * @param string $salt
 * @return $this
 */
$tag->createUnique(string $salt = "tag");
```
## isChanged
`public`: Check change status.
```php
/**
 * @return bool
 */
$tag->isChanged();
```
## getHashes
`public`: Get tag hashes.
```php
/**
 * @return array
 */
$tag->getHashes();
```
## compareHashes
`public`: Compare hashes.
```php
/**
 * @param array|Tag $comparable_hashes
 * @return array
 * @throws \Exception
 */
$tag->compareHashes($comparable_hashes = []);
```
## getRenderContent
`public`: Rendered content getter.
```php
/**
 * @return string
 */
$tag->getRenderContent();
```
## whenRender
`public`: Set when render closure.
```php
/**
 * @param \Closure $closure
 * @return $this
 */
$tag->whenRender(\Closure $closure);
```
## nameAppEnd
`public`: Add name in app end.
```php
/**
 * @param string $name_append
 * @return $this
 */
$tag->nameAppEnd(string $name_append);
```
## namePrepEnd
`public`: Add name prepend.
```php
/**
 * @param string $name_prepend
 * @return $this
 */
$tag->namePrepEnd(string $name_prepend);
```
## mapCollect
`public`: Collection tag map.
```php
/**
 * @param Collection|array $collection
 * @param \Closure $closure
 * @return Helpers
 * @throws \ReflectionException
 */
$tag->mapCollect($collection, \Closure $closure);
```
## toBottom
`public`: Type to bottom mode.
```php
/**
 * @param array $data
 * @return $this
 */
$tag->toBottom(...$data);
```
## isBottom
`public`: Check is bottom mode.
```php
/**
 * @return bool
 */
$tag->isBottom();
```
## dump
`public`: Dump this tag.
```php
/**
 * @return $this
 */
$tag->dump();
```

## ifAttribute
`public`: If attribute equal to value.
```php
/**
 * @param $attr
 * @param $value
 * @return bool
 */
$tag->ifAttribute($attr, $value);
```
## toExecute
`public`: Add method or methods to execute list.
```php
/**
 * @param $data
 * @return $this
 */
$tag->toExecute($data);
```
## toGlobalExecute
`public`: Add method or methods to global execute list.
```php
/**
 * @param $data
 * @return $this
 */
$tag->toGlobalExecute($data);
```
## quickInfusion
`public`: Quick infusion tag width data.
```php
/**
 * @param array $data
 * @return $this
 */
$tag->quickInfusion(array $data);
```
## render
`public`: Get the evaluated contents of the object.
```php
/**
 * @return string
 * @throws \Exception
 */
$tag->render();
```
## find
`public`: Find tags in content.
```php
/**
 * @param string $selector
 * @return Tag|FindCollection
 * @throws \Exception
 */
$tag->find(string $selector);
```
# Element methods
Each tag element has a corresponding method name for adding a new component to the parent.
```php
/**
 * @param ...$mixed
 * @return Tag
 */
 $tag->div([".myClass"])->a(["href" => "#link"], "Text");
```

# Magic methods

## Set attribute

Attribute determination methods:
```php
/**
 * @param ...$mixed
 * @return Tag
 */
$tag->setHref("http://google.com");
```

`setAccept`, `setAcceptCharset`, `setAccesskey`, `setAction`, `setAlign`, `setAlt`, `setAsync`, `setAutocomplete`, `setAutofocus`, `setAutoplay`, `setBgcolor`, `setBorder`, `setCharset`, `setChecked`, `setCite`, `setClass`, `setColor`, `setCols`, `setColspan`, `setContent`, `setContenteditable`, `setControls`, `setCoords`, `setData`, `setDatetime`, `setDefault`, `setDefer`, `setDir`, `setDirname`, `setDisabled`, `setDownload`, `setDraggable`, `setDropzone`, `setEnctype`, `setFor`, `setForm`, `setFormaction`, `setHeaders`, `setHeight`, `setHidden`, `setHigh`, `setHref`, `setHreflang`, `setHttpEquiv`, `setId`, `setIsmap`, `setKind`, `setLabel`, `setLang`, `setList`, `setLoop`, `setLow`, `setMax`, `setMaxlength`, `setMedia`, `setMethod`, `setMin`, `setMultiple`, `setMuted`, `setName`, `setNovalidate`, `setOpen`, `setOptimum`, `setPattern`, `setPlaceholder`, `setPoster`, `setPreload`, `setReadonly`, `setRel`, `setRequired`, `setReversed`, `setRole`, `setRows`, `setRowspan`, `setSandbox`, `setScope`, `setSelected`, `setShape`, `setSize`, `setSizes`, `setSpan`, `setSpellcheck`, `setSrc`, `setSrcdoc`, `setSrclang`, `setSrcset`, `setStart`, `setStep`, `setStyle`, `setTabindex`, `setTarget`, `setTitle`, `setTranslate`, `setType`, `setUsemap`, `setValue`, `setWidth`, `setWrap`

> Yes, all attributes that are in HTML5 have their own magic method.

## Set attribute If
```php
/**
 * @param boolean $eq|\Closure
 * @param ...$mixed
 * @return Tag
 */
$tag->setHrefIf(\Auth::user()->id == $id, "http://google.com");
```

`setAcceptIf`, `setAcceptCharsetIf`, `setAccesskeyIf`, `setActionIf`, `setAlignIf`, `setAltIf`, `setAsyncIf`, `setAutocompleteIf`, `setAutofocusIf`, `setAutoplayIf`, `setBgcolorIf`, `setBorderIf`, `setCharsetIf`, `setCheckedIf`, `setCiteIf`, `setClassIf`, `setColorIf`, `setColsIf`, `setColspanIf`, `setContentIf`, `setContenteditableIf`, `setControlsIf`, `setCoordsIf`, `setDataIf`, `setDatetimeIf`, `setDefaultIf`, `setDeferIf`, `setDirIf`, `setDirnameIf`, `setDisabledIf`, `setDownloadIf`, `setDraggableIf`, `setDropzoneIf`, `setEnctypeIf`, `setForIf`, `setFormIf`, `setFormactionIf`, `setHeadersIf`, `setHeightIf`, `setHiddenIf`, `setHighIf`, `setHrefIf`, `setHreflangIf`, `setHttpEquivIf`, `setIdIf`, `setIsmapIf`, `setKindIf`, `setLabelIf`, `setLangIf`, `setListIf`, `setLoopIf`, `setLowIf`, `setMaxIf`, `setMaxlengthIf`, `setMediaIf`, `setMethodIf`, `setMinIf`, `setMultipleIf`, `setMutedIf`, `setNameIf`, `setNovalidateIf`, `setOpenIf`, `setOptimumIf`, `setPatternIf`, `setPlaceholderIf`, `setPosterIf`, `setPreloadIf`, `setReadonlyIf`, `setRelIf`, `setRequiredIf`, `setReversedIf`, `setRoleIf`, `setRowsIf`, `setRowspanIf`, `setSandboxIf`, `setScopeIf`, `setSelectedIf`, `setShapeIf`, `setSizeIf`, `setSizesIf`, `setSpanIf`, `setSpellcheckIf`, `setSrcIf`, `setSrcdocIf`, `setSrclangIf`, `setSrcsetIf`, `setStartIf`, `setStepIf`, `setStyleIf`, `setTabindexIf`, `setTargetIf`, `setTitleIf`, `setTranslateIf`, `setTypeIf`, `setUsemapIf`, `setValueIf`, `setWidthIf`, `setWrapIf`

## Get attribute

```php
/**
 * @return string|array|boolean
 */
$tag->getSrc();
```

`getAccept`, `getAcceptCharset`, `getAccesskey`, `getAction`, `getAlign`, `getAlt`, `getAsync`, `getAutocomplete`, `getAutofocus`, `getAutoplay`, `getBgcolor`, `getBorder`, `getCharset`, `getChecked`, `getCite`, `getClass`, `getColor`, `getCols`, `getColspan`, `getContent`, `getContenteditable`, `getControls`, `getCoords`, `getData`, `getDatetime`, `getDefault`, `getDefer`, `getDir`, `getDirname`, `getDisabled`, `getDownload`, `getDraggable`, `getDropzone`, `getEnctype`, `getFor`, `getForm`, `getFormaction`, `getHeaders`, `getHeight`, `getHidden`, `getHigh`, `getHref`, `getHreflang`, `getHttpEquiv`, `getId`, `getIsmap`, `getKind`, `getLabel`, `getLang`, `getList`, `getLoop`, `getLow`, `getMax`, `getMaxlength`, `getMedia`, `getMethod`, `getMin`, `getMultiple`, `getMuted`, `getName`, `getNovalidate`, `getOpen`, `getOptimum`, `getPattern`, `getPlaceholder`, `getPoster`, `getPreload`, `getReadonly`, `getRel`, `getRequired`, `getReversed`, `getRole`, `getRows`, `getRowspan`, `getSandbox`, `getScope`, `getSelected`, `getShape`, `getSize`, `getSizes`, `getSpan`, `getSpellcheck`, `getSrc`, `getSrcdoc`, `getSrclang`, `getSrcset`, `getStart`, `getStep`, `getStyle`, `getTabindex`, `getTarget`, `getTitle`, `getTranslate`, `getType`, `getUsemap`, `getValue`, `getWidth`, `getWrap`

## Set HTML Event

```php
/**
 * @param ...$mixed
 * @return Tag
 */
$tag->onClick("alert('Hello!')");
```
`onAbort`, `onAfterprint`, `onAnimationend`, `onAnimationiteration`, `onAnimationstart`, `onBeforeprint`, `onBeforeunload`, `onBlur`, `onCanplay`, `onCanplaythrough`, `onChange`, `onClick`, `onContextmenu`, `onCopy`, `onCut`, `onDblclick`, `onDrag`, `onDragend`, `onDragenter`, `onDragleave`, `onDragover`, `onDragstart`, `onDrop`, `onDurationchange`, `onEnded`, `onError`, `onFocus`, `onFocusin`, `onFocusout`, `onFullscreenchange`, `onFullscreenerror`, `onHashchange`, `onInput`, `onInvalid`, `onKeydown`, `onKeypress`, `onKeyup`, `onLoad`, `onLoadeddata`, `onLoadedmetadata`, `onLoadstart`, `onMessage`, `onMousedown`, `onMouseenter`, `onMouseleave`, `onMousemove`, `onMouseover`, `onMouseout`, `onMouseup`, `onMousewheel`, `onOffline`, `onOnline`, `onOpen`, `onPagehide`, `onPageshow`, `onPaste`, `onPause`, `onPlay`, `onPlaying`, `onPopstate`, `onProgress`, `onRatechange`, `onResize`, `onReset`, `onScroll`, `onSearch`, `onSeeked`, `onSeeking`, `onSelect`, `onShow`, `onStalled`, `onStorage`, `onSubmit`, `onSuspend`, `onTimeupdate`, `onToggle`, `onTouchcancel`, `onTouchend`, `onTouchmove`, `onTouchstart`, `onTransitionend`, `onUnload`, `onVolumechange`, `onWaiting`, `onWheel`

> Oh yeah, I also have a magical function for every existing event in HTML5 (This is not the end of surprises).

## Set HTML Event If

```php
/**
 * @param boolean $eq|\Closure
 * @param ...$mixed
 * @return Tag
 */
$tag->onClickIf(\Auth::user()->id != $moderator_id, "alert('Don't touch');");
```

`onAbortIf`, `onAfterprintIf`, `onAnimationendIf`, `onAnimationiterationIf`, `onAnimationstartIf`, `onBeforeprintIf`, `onBeforeunloadIf`, `onBlurIf`, `onCanplayIf`, `onCanplaythroughIf`, `onChangeIf`, `onClickIf`, `onContextmenuIf`, `onCopyIf`, `onCutIf`, `onDblclickIf`, `onDragIf`, `onDragendIf`, `onDragenterIf`, `onDragleaveIf`, `onDragoverIf`, `onDragstartIf`, `onDropIf`, `onDurationchangeIf`, `onEndedIf`, `onErrorIf`, `onFocusIf`, `onFocusinIf`, `onFocusoutIf`, `onFullscreenchangeIf`, `onFullscreenerrorIf`, `onHashchangeIf`, `onInputIf`, `onInvalidIf`, `onKeydownIf`, `onKeypressIf`, `onKeyupIf`, `onLoadIf`, `onLoadeddataIf`, `onLoadedmetadataIf`, `onLoadstartIf`, `onMessageIf`, `onMousedownIf`, `onMouseenterIf`, `onMouseleaveIf`, `onMousemoveIf`, `onMouseoverIf`, `onMouseoutIf`, `onMouseupIf`, `onMousewheelIf`, `onOfflineIf`, `onOnlineIf`, `onOpenIf`, `onPagehideIf`, `onPageshowIf`, `onPasteIf`, `onPauseIf`, `onPlayIf`, `onPlayingIf`, `onPopstateIf`, `onProgressIf`, `onRatechangeIf`, `onResizeIf`, `onResetIf`, `onScrollIf`, `onSearchIf`, `onSeekedIf`, `onSeekingIf`, `onSelectIf`, `onShowIf`, `onStalledIf`, `onStorageIf`, `onSubmitIf`, `onSuspendIf`, `onTimeupdateIf`, `onToggleIf`, `onTouchcancelIf`, `onTouchendIf`, `onTouchmoveIf`, `onTouchstartIf`, `onTransitionendIf`, `onUnloadIf`, `onVolumechangeIf`, `onWaitingIf`, `onWheelIf`

## Quickly Class
And you can also quickly and easily insert your favorite classes with a short note:
```php 
/**  
 * @param $delimetr = "-"  
 * @return Tag  
 * @throws \Exception  
 */
 $tag->classMainPage(); // [class="main-page"]
 $tag->classMainPage("_"); // [class="main_page"]
 $tag->classMainPage("camel"); // [class="mainPage"]
 $tag->classMainPage("Camel"); // [class="MainPage"]
```

## Quickly Class If
The rules are the same as that of just a quick class.
```php 
/** 
 * @param $eq|\Closure 
 * @param $delimetr = "-"  
 * @return Tag  
 * @throws \Exception  
 */
 $route_name = \Route::currentRouteName();
 $tag->classActiveLinkIf($route_name === "home"); // [class="active-link"]
 $tag->classActiveLinkIf($route_name === "home", "_"); // [class="active_link"]
 ...
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MTE2OTkyMzldfQ==
-->