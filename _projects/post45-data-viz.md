---
title: "Post45 Data Visualizations"
collection: projects
type: data-viz
permalink: /project/post45-data-viz
excerpt: ''
---

## Number of Articles Published by Post45

<iframe width="100%" height="514" frameborder="0"
  src="https://observablehq.com/embed/@arthurzwang-workspace/post45-published-articles-public-5-8-23@794?cells=articleChart"></iframe>

## Review and Publication Timelines: _Post45_ vs. Other Journals

  <iframe width="100%" height="790" frameborder="0"
  src="https://observablehq.com/embed/@arthurzwang-workspace/post45-timeline-comps-may-9-2023@276?cells=compsChart"></iframe>


Color scheme for the visualizations above: [Cheysson Palette](https://observablehq.com/@tomshanley/cheysson-color-palettes) licensed under ISC License (ISC) Copyright 2021 [Tom Shanley](https://observablehq.com/@tomshanley)

## Post45 Submission Outcomes since 2020 (excluding special issues)
<figure>
	<object type="image/svg+xml" data="../images/outcomes_sankey.svg" class="fitvidsignore"></object>
	<figcaption>
		Image created with <a href="https://sankeymatic.com/build/">SankeyMATIC</a>
	</figcaption>
</figure>


<!-- Script for resizing iframes. Adapted from: https://github.com/observablehq/examples/blob/main/iframe-resize/index.html -->
<script type="module">

// Select the embed iframe.
const iframes = document.querySelectorAll(".embed");

// The Embedly protocol is to send the height as part of a stringified object.
// In this example, the resize message is the only message being sent; however,
// the checks are good practice, lest we try to interpret unrelated messages as
// resize events. https://docs.embed.ly/v1.0/docs/provider-height-resizing
function onMessage(message) {
	const source = Array.from(iframes).find(i => i.contentWindow === message.source);
	if (!source) return;
  // if (message.source !== iframe.contentWindow) return;
  let {data} = message;

  // If message isn’t valid JSON, it must not be our resize event.
  if (typeof data === "string") {
    try {
      data = JSON.parse(data);
    } catch (ignore) {
      return;
    }
  }

  // Make sure it’s the resize event.
  if (data.context !== "iframe.resize") return;

  // Set the iframe’s height!
  source.style.height = `${data.height}px`;
}

// Attach our listener for the message from the iframe
addEventListener("message", onMessage);

</script>