# HTML Opaque, Trustworthy, Declarative Ads Markup (HOTDAM)

One key requirement in order to develop a healthy ecosystem for advertising is to load ads in a way that is
sufficiently privacy-preserving. The current primary proposal to achieve that is
[Fenced Frames](https://github.com/shivanigithub/fenced-frame). Fenced Frames have many interesting properties, but 
[recent Privacy CG discussions](https://docs.google.com/document/d/1DZEhS1UHJ1PKxt5ZwKmn5LZ4bo10UFyNXeLp2dUuzRM/edit#)
indicate that it may be challenging for them to address all the use cases stakeholders have for them at once.
While it is naturally tempting to design generic solutions, that is not always the best approach. Creating new
HTML elements is not in principle an insuperable task, and in some cases it is better to kill two birds with 
two stones.

Note that this proposal reuses ideas from Fenced Frames that work for both, instead of reinventing them.

Tk notes
* **bundles**: only load bundles and allow no further network interaction. This enables the use of arbitrary sizes.
* **video**: require that the `src` be static and forbid `autoplay`.
* **top level**: content inside the `ad` element cannot know that it is not at the top level, media queries work on 
  that assumption so that ads can easily be responsive.
