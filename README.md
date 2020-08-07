# New Server Side Render Component
The core WordPress component to render dynamic blocks (`<ServerSideRender />`) is not optimized and currently results in a poor user experience as demonstrated below (for the [Flexible FAQs](https://wpgoplugins.com/plugins/flexible-faqs/) block).<br><br>

<p align="center" style="margin:100px;">
  <img src="https://user-images.githubusercontent.com/1482075/89642033-e4a0ba00-d8aa-11ea-9449-96e9fb9299e4.gif" width="700">
</p>

<br>Notice how the *whole* block content area is replaced with a spinner whenever a block attribute is updated.

To address this issue, a new `<ServerSideRenderX />` component has been developed as a direct replacement for `<ServerSideRender />`. This new component is similar to the previous one except it uses the **previously rendered HTML as the placeholder**. This results in a *much* smoother transition between render states.<br><br>

<p align="center">
  <img src="https://user-images.githubusercontent.com/1482075/89642258-6395f280-d8ab-11ea-82b5-6cbba42ae72f.gif" width="700">
</p>

<br>A spinner is also included along with the previous HTML as an indicator that the content is being updated.

## Usage

Add the `server-side-render-x.js` file to the relevant place in your plugin (e.g. `/src/block/components`) and include it in your code as you would for any other component.

Then implement the new component in exactly the same way as for `<ServerSideRender />`.

    <ServerSideRenderX
      block="my-plugin/my-block"
      attributes={attributes}
    />

There's also an additional (optional) `prop` available to specify the location for the spinner:

    <ServerSideRenderX
      block="my-plugin/my-block"
      attributes={attributes}
      spinnerLocation={{right: 0, top: 10, unit: 'px'}}
    />

The above value for `spinnerLocation` is the default value used internally, so leave this blank unless you need to specifically change it.
