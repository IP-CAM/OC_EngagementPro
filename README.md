# OpenCart_EngagementPro
An <a href="http://opencart.com/" target="_blank">OpenCart</a> extension that tracks and reports data on customer engagement. 

<h3>About</h3>
<h4>This extension has two major features:</h4>
a) <strong>Search</strong>: Generates report on specific search queries made by customers in the store front.
<br>
b) <strong>Repeat Customers</strong>: Generates report on customers who have made repeat purchases.

<h3>Requirements</h3>
<ul>OpenCart v 2.0.3.1 && PHP >=5.3</ul>

<h3>Install</h3>

1) Upload the following files to your OpenCart store root directory from the oc_epro folder:

<ul><li>admin/controller/report/engagement_pro.php</li>
<li>admin/model/report/engagment_pro.tpl</li>
<li>admin/view/template/report/engagment_pro.tpl</li>
<li>admin/language/english/report/engagment_pro.php</li>
<li>catalog/controller/account/engagment_pro.php</li>
<li>catalog/model/account/engagment_pro.php</li></ul>

2)

a) Upload epro_install.ocmod.xml modification file to the system folder. Under Admin Home > Modifications click refresh to activate extension.  

b) Or directly modify the following files (not recommended):

<h5>Add Engagement PRO search query script</h5>

<ul>catalog/controller/common/header.php</ul>

<ul>Add  <code>$this->document->addScript('catalog/view/javascript/engagement_search.js');</code> before <code>$data['base'] = $server;</code></ul>

<h5>Add Engagement PRO link to admin menu</h5>

<ul>admin/view/template/common/menu.tpl</ul>

<ul>Add  <code>&#x3C;li&#x3E;&#x3C;a href=&#x22;&#x3C;?php echo str_replace(&#x27;report/customer_credit&#x27;, &#x27;report/engagement_pro&#x27;, $report_customer_credit); ?&#x3E;&#x22;&#x3E;Engagement PRO&#x3C;/a&#x3E;&#x3C;/li&#x3E;</code> after <code>&#x3C;li&#x3E;&#x3C;a href=&#x22;&#x3C;?php echo $report_customer_credit; ?&#x3E;&#x22;&#x3E;&#x3C;?php echo $text_report_customer_credit; ?&#x3E;&#x3C;/a&#x3E;&#x3C;/li&#x3E;</code></ul>

3. Enable permissions

<ul>Under User Groups, check "report/engagementpro" in Access Permission and Modify Permission</ul>

<h3>Docker (on dev branch)</h3>

1. Checkout dev branch
2. docker-compose up
3. Visit http://localhost:8080 for OpenCart installation
4. Visit http://localhost:8080/admin (user: admin, password: admin) to access the OpenCart admin
5. Under Admin Home > Modifications click refresh to activate extension.  
6. Under User Groups, check "report/engagementpro" in Access Permission and Modify Permission.  
7. Engagment PRO is accessible at http://localhost:8080/admin/index.php?route=report/engagement_pro

<h4>Running tests</h4>
1. <code>sudo docker <container_name> exec --it bash</code>
2. In /var/www/html run <code>vendor/bin/phpunit --testsuite admin-tests</code>

<h3>Note</h3>
This extension may not work with a modified OpenCart store or in conjunction with other 3rd party extensions. 

<h3>TODO</h3>
<ul>Add cart abandonment analytics</ul>
<ul>Export CSV & Filter options for Repeat Customers panel</ul>
<ul>Port to other versions of OC</ul>
