### Reveal.js-based presentation on Labeling Strategies for Esri JavaScript Clients

### Introduction

### Dev Note

The dojo-based Esri library can have trouble loading off-screen maps.  I had to use this hack to get the map to size correctly

	Reveal.addEventListener( 'slidechanged', function( event ) {
		var frames = $(event.currentSlide).find("iframe");
		if(frames && frames[0]) {
			if(frames[0].src.indexOf("_dojo_") > -1) {
				frames[0].contentDocument.location.reload(true);
				console.log('reloaded frame');
			} 
		}
	} );

### Using tile layers for labeling