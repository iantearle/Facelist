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
