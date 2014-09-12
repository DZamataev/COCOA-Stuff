# GGReadabilityParser
-------------------------------
GGReadabilityParser is a complete rewrite of the current GGReadability, this new version is
almost four times as quick aswell as providing much better results.

The use is simple, you have to create a new GGReadabilityParser object like this:
	
	GGReadabilityParser * readability = [[GGReadabilityParser alloc] initWithURL:[NSURL URLWithString:@"someURLHere"]
                                                  						 options:GGReadabilityParserOptionClearStyles|GGReadabilityParserOptionClearLinkLists|GGReadabilityParserOptionFixLinks|GGReadabilityParserOptionFixImages|GGReadabilityParserOptionRemoveHeader|GGReadabilityParserOptionRemoveIFrames
                                       						   completionHandler:^(NSString *content)
    {
    	// handle returned content
    }
                                              						errorHandler:^(NSError *error) 
    {
    	// handle error returned
    }];
    
This will create object, it requires a NSURL for the URL, a list of options that you want the parser to carry out, a completion handler block and an error block.

To get readability to parser just call:

	[readability render];
	
If you want to check the load progress of it then you can simply check the loadProgress ivar - you can also bind to this.

## Improvements in this fork
------------------------------------
This version is built against https://github.com/DZamataev/GDataXML-HTML parsing lib which runs both on iOS and OSX.
Also some improvements to the algorithm is currently in progress. The goal is to make GGReadabilityParser work with iOS WebView, which involves parsing non-valid HTML and performing image resource loading and caching locally along with modifying the links in the resulting document to point to the local resources.


## Licence
GGReadabilityParser is free to use for everyone.

Please leave credit in your application where it is due - its only nice to :)

