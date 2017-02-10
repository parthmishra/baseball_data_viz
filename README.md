An interactive visualization created with Dimple.js and D3

## Summary

This visualization is designed to highlight a bivariate relationship between various baseball player's weight and their batting average. Additionally, this graphs facets the relationship by the handedness of the batter e.g. Left, Right, or Switch hitter. Through this visualization, I hope to highlight the differences in player performance from a multi-dimensional perspective using some rarely correlated metrics. Interestingly enough, light lefties seem to be more likely to have a higher batting average than their right handed counterparts.Additionally, switch hitters, who are thought to have a specific strategic value don't seem to perform all that much better than pure righties or lefties across all weight sizes. Perhaps the key to a better batting average is really just to weigh less!

My final visualization of this relationship is in the form of a D3 scatter plot that features an interactive legend that allows readers to toggle between the different batting styles while observing the relationship between weight and batting average. The live example can be found in my [bl.ocks page](https://bl.ocks.org/parthmishra/e928a5add86c3d302037c922438afe54).


## Design and Feedback

My first attempt at this visualization is to find a plot type that represented the relationship between weight and home runs. The plan is to find a good base plot that cleanly displays all the data points available before moving on and adding interaction/animation. This way I don't waste time trying to iterate on a plot that wasn't very clear to readers in the first place. The results of my first iteration is as follow:

![Attempt 1](/images/attempt1.png)

I solicited feedback on this plot and got a few critiques right off the bat:

* Circles are too big and make large blobs thus making it hard to distinguish some points
* The relationship being shown is clear
* However, the data just looks normally distributed, the *purpose* of the plot is unclear

The feedback I got was pretty much expected as I hadn't yet faceted the data or included any means of interaction yet.

***

In the second attempt, I actually moved away from D3 as I could not figure out how to make it work like I wanted too whereas dimple was slightly easier to work with. Using dimple, I was able to achieve the handedness faceting on the scatter plot that I was hoping to show. The resulting plot:

![Attempt 2](/images/attempt2.png)

Soliciting feedback for this plot, I got several critiques:

* No title [oops!] and legend is unclear
* Not immediately obvious what this is trying to convey, takes a minute to understand
* Tooltips are nice!
* Weight axis is very cluttered

In my excitement at getting a plot to even work, I clearly had neglected some clarity aspects. Dimple unfortunately is very hard to customize (axes...) but D3 is very hard to just use in general so at this point I'm at a crossroads. My goal for the final iteration will be to provide as much clarity as possible using Dimple.

***

In the third iteration, I moved heavily away from the previous dimple graph as it was way too hard to do even basic things like adjust ticks on the axis. So I went back to D3 and with the help of some wonderful Mike Bostock tutorials/examples, I was able to put together a nice scatter plot that alleviated some of the previous issues I had. A live version is available via [this bl.ocks page](https://bl.ocks.org/parthmishra/e928a5add86c3d302037c922438afe54) or you can view the static image below:

![Attempt 3](/images/attempt3.png)

As you can see, I moved away from home runs as the metric to look at due to a conversation with someone who informed me that batting average is more likely predictor of performance for *most* players whereas home runs tend to be dominated by the 4th spot clean up hitters. With that bit of domain knowledge, I shifted my focus to batting average and a more interesting result came about! In order to address some of the concerns from previous feedback rounds, I added a descriptive title although it's hard to not wordily describe a multivariate relationship. With D3, I was able to clean up the axes pretty handily compared to Dimple which greatly improved readability of the plot. The color scheme for the handedness of the players is discrete since there is no inherent ordinance to these data. While cluttered upon initial view, I added an interactive legend that allows the reader to focus in on certain batting styles while still having some context as to the rest of the data.

The feedback I got for this plot, in my opinion, was mostly non-consequential. I received a suggestion for tooltips that had player name on it which I struggled to implement and decided not too because my overall focus is on the general relationships rather than examining the outliers. Another suggestion I got was to incorporate zoom when selecting the styles, however I elected not to put that in since I think the data is only relevant when given context of the other data. This is why I liked my choice to just alter the opacity as it allows the reader to focus in one aspect while still remaining cognizant of the surrounding data.

***

With my last iteration, I made some minor adjustments including making the whole graph bigger (unfortunately the tradeoff is I can't put it into a bl.ock so you'll have to serve the index.html page locally if you want a live version), the dots bigger, and adding an explanatory paragraph that aims to guide the reader through the graphic. I removed values of zero that weren't adding much to the data and finally, I included a source to make it look more official.


## Resources

* https://bl.ocks.org/d3noob/23e42c8f67210ac6c678db2cd07a747e
*  https://leanpub.com/D3-Tips-and-Tricks/read#leanpub-auto-update-data-dynamically---on-click
* http://jsfiddle.net/V3jt5/1/
* http://bl.ocks.org/d3noob/e99a762017060ce81c76
