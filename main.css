function get(page, cb) {
  var modifiedURL = "https://crossorigin.me/" + page;
  var xhr = new XMLHttpRequest();
  xhr.addEventListener("readystatechange", function() {
    if (xhr.readyState === 4) {
      cb(xhr.response);
    }
  });
  xhr.open("GET", modifiedURL, true);
  xhr.send();
}

function update(doc) {
  var toc = document.getElementById("toc");

  // If doc, we're using this in production and doc is a document.
  if (doc) {
    var links = doc.querySelectorAll(".wiki-page-link");
    var hrefs = [];
    var texts = [];
    for (var i = 0; i < links.length; i++) {
      var link = links[i];
      var href = "https://github.com" + link.getAttribute("href");
      hrefs.push(href);
      texts.push(link.textContent);
    }
  }

  // Otherwise, we're testing and shall use placeholder values.
  else {
    var hrefs = ["#", "#", "#", "#"];
    var texts = ["Hello World", "Home", "Orangutan", "This is a very long title"];
  }

  texts.forEach(function(text, i) {
    var text = texts[i];
    var href = hrefs[i];
    var a = document.createElement("a");
    a.setAttribute("href", href);
    a.appendChild(document.createTextNode(text));
    a.classList.add("wiki-page-link");

    // When the user clicks on it, load the page related to it.
    a.onclick = function(evt) {
      evt.preventDefault();
      loadPage(href);
      return false;
    };

    toc.appendChild(a);
  });
}

function loadPage(href) {
  var container = document.getElementById("container");
  get(href, function(res) {
    var parser = new DOMParser();
    var doc = parser.parseFromString(res, "text/html");
    var wikiBody = doc.getElementById("wiki-body");
    while (container.firstChild) {
      container.removeChild(container.firstChild);
    }
    container.appendChild(wikiBody);
  });
}

get("https://github.com/liam4/scratch-api-unofficial-docs/wiki", function(res) {
  var parser = new DOMParser();
  var doc = parser.parseFromString(res, "text/html");
  update(doc);
});


// update();
