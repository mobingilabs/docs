# Overview

&lt;?php include_once \_DIR_.'/../header.php';

require **DIR**.'/../Parsedown.php'; require **DIR**.'/../ParsedownExtra.php'; require **DIR**.'/../ParsedownExtraPlugin.php';

// $Parsedown = new Parsedown\(\); $parser = new ParsedownExtraPlugin\(\);

$content = file_getcontents\(realpath\(\_\_DIR_ . '/../..'\).'/markdown/enterprise/doc-api.md'\);

?&gt;

```text
<aside class="col-sm-3 sidebar">
    <?php include_once realpath(__DIR__ . '/../..').'/markdown/enterprise/doc-api-sidebar.md.php'; ?>
</aside>
<!-- END Sidebar -->
```

## API Reference \(Enterprise Edition\) {#api-reference}

 Mobingi API is organized around REST.  
 Our API has predictable, resource-oriented URLs. We support CORS \(Cross-Origin Resource Sharing\), allowing you to interact securely with our API. text\($content\); ?&gt;

&lt;?php include_once \_DIR_.'/../footer.php'; ?&gt;

  
$\("table"\).addClass\("table table-bordered table-striped"\);  


