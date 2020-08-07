# New Server Side Render Component
Introducing the `<ServerSideRenderX />` component as a direct replacement for the core `<ServerSideRender />` component, which is not optimized and provides a poor user experience as demonstrated below for the [Flexible FAQs](https://wpgoplugins.com/plugins/flexible-faqs/) block component.<br><br>

<p align="center" style="margin:100px;">
  <img src="https://user-images.githubusercontent.com/1482075/89642033-e4a0ba00-d8aa-11ea-9449-96e9fb9299e4.gif" width="700">
</p>

<br>The `<ServerSideRenderX />` component is almost identical to the core component except it uses the **previously rendered HTML as the placeholder**. This results in a *much* smoother transition between render states.<br><br>

<p align="center">
  <img src="https://user-images.githubusercontent.com/1482075/89642258-6395f280-d8ab-11ea-82b5-6cbba42ae72f.gif" width="700">
</p>

<br>
## Usage

Add the `server-side-render-x.js` file to the relevant place in your plugin (e.g. `/src/block/components`) and include in your code as you would for any other component.

Then use it in exactly the same way as `<ServerSideRender />` is used.

    <ServerSideRenderX
	  block="my-plugin/my-block"
      attributes={attributes}
	/>

The only difference is there is an additional optional `prop` to specify the location for the spinner:

    <ServerSideRenderX
	  block="my-plugin/my-block"
      attributes={attributes}
      spinnerLocation={{right: 0, top: 10, unit: 'px'}}
	/>

The above value for `spinnerLocation` is the default used internally so leave this blank unless you need to specifically change it.
