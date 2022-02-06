<code>
	<script>
	const highlights = document.querySelectorAll("div.highlight")

	highlights.forEach(div=> {
		const copy = document.createElement("button")
		copy.innerHTML = "copy"

		copy.addEventListener("click", handleCopyClick)

		div.append(copy)
	})

	const copyToClipboard = str => {
  const el = document.createElement("textarea") // Create a <textarea> element
  el.value = str // Set its value to the string that you want copied
  el.setAttribute("readonly", "") // Make it readonly to be tamper-proof
  el.style.position = "absolute"
  el.style.left = "-9999px" // Move outside the screen to make it invisible
  document.body.appendChild(el) // Append the <textarea> element to the HTML document
  const selected =
    document.getSelection().rangeCount > 0 // Check if there is any content selected previously
      ? document.getSelection().getRangeAt(0) // Store selection if found
      : false // Mark as false to know no selection existed before
  el.select() // Select the <textarea> content
  document.execCommand("copy") // Copy - only works as a result of a user action (e.g. click events)
  document.body.removeChild(el) // Remove the <textarea> element
  if (selected) {
    // If a selection existed before copying
    document.getSelection().removeAllRanges() // Unselect everything on the HTML document
    document.getSelection().addRange(selected) // Restore the original selection
  }
}

function handleCopyClick(evt) {
  // get the children of the parent element
  const { children } = evt.target.parentElement
  // grab the first element (we append the copy button on afterwards, so the first will be the code element)
  // destructure the innerText from the code block
  const { innerText } = Array.from(children)[0]
  // copy all of the code to the clipboard
  copyToClipboard(innerText)
  // alert to show it worked, but you can put any kind of tooltip/popup to notify it worked
  alert(innerText)
}



</script>

<style>

	div.highlight button {
	  color: #adb5bd;
	  box-sizing: border-box;
	  transition: 0.2s ease-out;
	  cursor: pointer;
	  user-select: none;
	  background: rgba(0, 0, 0, 0.15);
	  border: 1px solid rgba(0, 0, 0, 0);
	  padding: 5px 10px;
	  font-size: 0.8em;
	  position: absolute;
	  top: 0;
	  right: 0;
	  border-radius: 0 0.15rem;
	}


</style>
# odhis_one_package

checkout the latest test version at [pypi](https://test.pypi.org/project/odhis-one-3ud49/0.0.3/#history)

install version <div class="highlight">
<code>pip install -i https://test.pypi.org/simple/ odhis-one-3ud49==0.0.3</code>
<button>Copy</button>

</div>
</code>

