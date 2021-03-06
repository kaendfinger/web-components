#### 0.10.1
  * Added the `CustomElementProxy` annotation. This can be added to any class
    which proxies a javascript custom element and is the equivalent of calling
    `registerDartType`. In order to use this you will need to be using the
    `initialize` package, and call its `run` method from your main function. It
    is also recommended that you include the transformer from that package to
    remove the use of mirrors at runtime, see
    [initialize](https://github.com/dart-lang/initialize) for more information.

#### 0.10.0
  * Updated to the `0.5.1` js version.
  * **Breaking Change** To remain consistent with the js repository all the
    `platform.js` has been replaced with `webcomponents.js`. Also, the default
    file is now unminified, and the minified version is called
    `webcomponents.min.js`.

#### 0.9.0+1
  * Remove all `.map` and `.concat.js` files during release mode.

#### 0.9.0
  * Updated to platform version 0.4.2, internally a deprecated API was removed,
    hence the bump in the version number.

  * split dart_support.js in two. dart_support.js only contains what is
    necessary in order to use platform.js,
    interop_support.js/interop_support.html can be imported separately when
    providing Dart APIs for js custom elements.

#### 0.8.0
  * Re-apply changes from 0.7.1+1 and also cherry pick 
    [efdbbc](https://github.com/polymer/CustomElements/commit/efdbbc) to fix
    the customElementsTakeRecords function.
  * **Breaking Change** The customElementsTakeRecords function now has an
    an optional argument `node`. There is no longer a single global observer,
    but one for each ShadowRoot and one for the main document. The observer that
    is actually used defaults to the main document, but if `node` is supplied
    then it will walk up the document tree and use the first observer that it
    finds.

#### 0.7.1+2
  * Revert the change from 0.7.1+1 due to redness in FF/Safari/IE.

#### 0.7.1+1
  * Cherry pick [f280d](https://github.com/Polymer/ShadowDOM/commit/f280d) and
    [165c3](https://github.com/Polymer/CustomElements/commit/165c3) to fix
    memory leaks.

#### 0.7.1
  * Update to platform version 0.4.1-d214582.

#### 0.7.0+1
  * Cherry pick https://github.com/Polymer/ShadowDOM/pull/506 to fix IOS 8.

#### 0.7.0
  * Updated to 0.4.0-5a7353d release, with same cherry pick as 0.6.0+1.
  * Many features were moved into the polymer package, this package is now
    purely focused on polyfills.
  * Change Platform.deliverDeclarations to 
    Platform.consumeDeclarations(callback).
  * Cherry pick https://github.com/Polymer/ShadowDOM/pull/505 to fix mem leak.

#### 0.6.0+1
  * Cherry pick https://github.com/Polymer/ShadowDOM/pull/500 to fix
    http://dartbug.com/20141. Fixes getDefaultComputedStyle in firefox.

#### 0.6.0
  * Upgrades to platform master as of 8/25/2014 (see lib/build.log for details).
    This is more recent than the 0.3.5 release as there were multiple breakages
    that required updating past that.
  * There is a bug in this version where selecting non-rendered elements doesn't
    work, but it shouldn't affect most people. See 
    https://github.com/Polymer/ShadowDOM/issues/495.

#### 0.5.0+1
  * Backward compatible change to prepare for upcoming change of the user agent
    in Dartium.

#### 0.5.0
  * Upgrades to platform version 0.3.4-02a0f66 (see lib/build.log for details).

#### 0.4.0
  * Adds `registerDartType` and updates to platform 0.3.3-29065bc
    (re-applies the changes in 0.3.5).

#### 0.3.5+1
  * Reverts back to what we had in 0.3.4. (The platform.js updates in 0.3.5 had
    breaking changes so we are republishing it in 0.4.0)

#### 0.3.5
  * Added `registerDartType` to register a Dart API for a custom-element written
    in Javascript.
  * Updated to platform 0.3.3-29065bc

#### 0.3.4
  * Updated to platform 0.2.4 (see lib/build.log for details)
