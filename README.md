# WordPress-JSON-AJAX
This is rewrited wordpress core file admin-ajax.php to work with JSON data in request
You can add it to to you wordpress plugin or theme
Or you can create new folder in wp root named, for example, 'api' and put it there
After this part is done, you can define path to this file as global js variable
For example, use this code before closing tag <body> in file footer.php of your theme

<script type='text/javascript'>
    /* <![CDATA[ */
    window.ajaxurl  = '<?php echo site_url() . '/api/json-rpc.php'; ?>';
    /* ]]> */
</script>

And create request which will be data in body as JSON

For example

let data = { key: value };
fetch( ajaxurl, {
    method: 'POST',
    'Content-Type': 'application/json;charset=utf-8',
     body: JSON.stringify(data)
 });
