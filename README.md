# Toggle Button

> Pimp your checkbox! 

![Screenshot with off state, on state and custom color](preview.png)

Scalable SVG toggle buttons, HTML/CSS only, no dependencies, yeah!
Aims for a fail-well approach, if svg is somehow not supported, the Regular Joe&trade; checkbox can be displayed.

Currently uses CSS custom properties, [limited support](http://caniuse.com/#search=css%20variables), planned for an own branch.

## Usage

Include the contents of toggle-button.css.

Include the SVG code **once** in your HTML:

	<svg version="1.1" x="0px" y="0px" enable-background="new 0 0 48 24" xml:space="preserve" style="display: none;">
		<symbol id="toggle-button" viewBox="0 0 48 24">
			<g>
				<path class="toggle-button-panel-body" fill="currentColor" d="M12,24C5.7,24,0.5,18.8,0.5,12.5S5.7,1,12,1h24c6.3,0,11.5,5.2,11.5,11.5S42.3,24,36,24H12z"/>
				<path class="toggle-button-panel-border" fill="currentColor" d="M36,1c6.1,0,11,4.9,11,11c0,6.1-4.9,11-11,11H12C5.9,23,1,18.1,1,12C1,5.9,5.9,1,12,1H36 M36,0H12
				C5.4,0,0,5.4,0,12v0c0,6.6,5.4,12,12,12h24c6.6,0,12-5.4,12-12v0C48,5.4,42.6,0,36,0L36,0z"/>
			</g>
			<g>
				<path class="toggle-button-knob-body" fill="currentColor" d="M12.1,23.5C5.7,23.5,0.6,18.4,0.6,12S5.7,0.5,12.1,0.5S23.6,5.7,23.6,12S18.4,23.5,12.1,23.5z"/>
				<path class="toggle-button-knob-border" fill="currentColor" d="M12.1,1c6.1,0,11,4.9,11,11s-4.9,11-11,11s-11-4.9-11-11S6,1,12.1,1 M12.1,0c-6.6,0-12,5.4-12,12
				s5.4,12,12,12s12-5.4,12-12S18.7,0,12.1,0L12.1,0z"/>
			</g>
		</symbol>			
	</svg>

Use it in your forms:

	<label for="cb-1">
		<input type="checkbox" id="cb-1" class="toggle-button-trigger">
		<svg class="toggle-button">
			<use xlink:href="#toggle-button"/>
		</svg>
		Bluetooth
	</label>

## Custom Colors

The color of every part is customizable, just assign an additional class to the checkbox:

	<label for="cb-3">
		<input type="checkbox" id="cb-3" class="toggle-button-trigger">
		<svg class="toggle-button toggle-button--error">
			<use xlink:href="#toggle-button" />
		</svg>
		Fancy color mode
	</label>

and the CSS:

	.toggle-button-trigger:checked + .toggle-button.toggle-button--error .toggle-button-panel-body,
	.toggle-button-trigger:checked + .toggle-button.toggle-button--error .toggle-button-panel-border,
	.toggle-button-trigger:checked + .toggle-button.toggle-button--error .toggle-button-knob-border {
		color: red;
	}



## TODO:

- [ ] Detach CSS custom properties version to own branch
- [ ] Compatibility tests
- [ ] Provide SASS version
- [ ] Accessibility


Kudos to [Sara Soueidan](http://tympanus.net/codrops/2015/07/16/styling-svg-use-content-css/) for the detailed article, thanks!