<html lang="da">
<head>
<title>Test</title>
<meta charset="UTF-8">
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
</head>
<body>
<div class="container">
<h1>Nyheder fra sundhedsstyrelsen.dk</h1>
<?php
   $rss = new DOMDocument();
   $rss->load('https://sundhedsdatastyrelsen.dk/da/feeds/nyheder');
   $feed = array();
   foreach ($rss->getElementsByTagName('item') as $node) {
      $item = array(
                'title' => $node->getElementsByTagName('title')->item(0)->nodeValue,
                'desc' => $node->getElementsByTagName('description')->item(0)->nodeValue,
                'link' => $node->getElementsByTagName('link')->item(0)->nodeValue,
                );
      array_push($feed, $item);
   }
   $limit = 60;
   for($x=0;$x<$limit;$x++) {
      $title = str_replace(' & ', '&amp; ', $feed[$x]['title']);
      $link = $feed[$x]['link'];
      $description = $feed[$x]['desc'];
      echo '<p><b><a href="'.$link.'" target="_blank">'.$title.'</a></b></p>';
      echo '<p>'.$description.'</p>';
   }
?>
</div>
</body>
</html>
