# New Server Side Render Component
Introducing the `<ServerSideRenderX />` component as a direct replacement for the core `<ServerSideRender />` component.

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
