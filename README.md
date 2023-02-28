# WPMediaFetch_WPGETRESULT-
WP Get or Fetch Attachment via getResult() WP native function custom query 

<a href="https://codex.wordpress.org/images/2/25/WP4.4.2-ERD.png"> WP Database Description </a> <br />

```PHP

function get_icon_for_attachment($post_id) {
  $base = get_template_directory_uri() . "/images/icons/";
  $type = get_post_mime_type($post_id);
  switch ($type) {
    case 'image/jpeg':
    case 'image/png':
    case 'image/gif':
      return $base . "image.png"; break;
    case 'video/mpeg':
    case 'video/mp4': 
    case 'video/quicktime':
      return $base . "video.png"; break;
    case 'text/csv':
    case 'text/plain': 
    case 'text/xml':
      return $base . "text.png"; break;
    default:
      return $base . "file.png";
  }
}
// call it like this:
echo '<img src="'.get_icon_for_attachment($my_attachment->ID).'" />';

```

Source: <a href="https://developer.wordpress.org/reference/functions/get_post_mime_type/"> Database MIME TYPE </a> <br />
