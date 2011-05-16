Facelist
=============

Built for the sole purpose of providing a Facebook style autosearch.

Facelist provides an autocomplete suggestive search built with jQuery and a little CSS3 wizardry. Its easy to set up, implement and is completely open source, meaning you can edit, cannibalise and change the underlying code.

Implementation
-------

### Calling Facelist

The simplest implementation to get Facelist working is by adding the code below. This will apply a Facelist control to every input on your page.

	$(function(){ $("input[type=text]").faceList(data); });

### Enabling Multiple Uses

To enable multiple Facelists containing different data make your selections with different calls:
	
	$(function(){ $("div.anclass input").faceList(data); $("#anid input").faceList(other_data); });

### Defining URI

You can define a URI for the data:

	$("input[type=text]").faceList("http://yoursite.com/path/to/script", {minChars: 3, matchCase: true});

### AJAX Call

An example of the PHP used for an AJAX call to a script on your site can be made like so:

	$input = $_GET["q"]; $data = array(); $query = mysql_query("SELECT * FROM table WHERE field LIKE '%$input%'"); while ($row = mysql_fetch_assoc($query)) { $json = array(); $json['value'] = $row['id']; $json['name'] = $row['username']; $json['image'] = $row['user_photo']; $data[] = $json; } header("Content-type: application/json"); echo json_encode($data);

### MIT License

Copyright (c) 2011 Ian Tearle

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
