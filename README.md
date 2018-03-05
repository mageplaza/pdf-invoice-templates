# Mageplaza PDF Invoice Templates for Magento 2

## Overview

Mageplaza PDF Invoice for Magento 2 solves problems that online store have when they send billing documents to their customers. The module helps them simplify the jobs, attach PDF documents into emails with amazing easy-to-customize templates.

With [Magento 2 PDF Invoice](https://www.mageplaza.com/magento-2-pdf-invoice-extension/), the module can guarantee customer’s records in a consistent format, make sure that the fixed design of invoices will be handled nicely. Its vital job simply is delivering all available content from your order/invoice/shipment/credit memo onto a PDF file, and sending it via email systems, without missing a field. An additional great news is, it will send the PDF file automatically right after the invoice documentation is generated! Install the extension, peek at configurations a bit then the rest is up to automation chains.

## Magento 2 PDF Invoices

PDF Invoice for Magento 2 is a must-have for your store. In case you want more information about this outstanding extension, you should refer these links below:
* [What is Magento 2 PDF Invoice](https://www.mageplaza.com/magento-2-pdf-invoice-extension/)
* Demo links: [Frontend](http://pdfinvoice.demo.mageplaza.com/) | [Backend](http://pdfinvoice.demo.mageplaza.com/admin/sales/order/index/key/1d0ce6ee95e14d58dc692bbbc34c0ded0b345229d42a6dd73fb6caa60209a56f/)
* [Installation Guide](https://www.mageplaza.com/install-magento-2-extension/)
* [User Guide](https://docs.mageplaza.com/pdf-invoice-m2/)

Download the following Templates for your custom design:

* [PDF Invoice](https://github.com/mageplaza/pdf-invoice-templates/tree/master/invoice)
* [PDF Order](https://github.com/mageplaza/pdf-invoice-templates/tree/master/order)
* [PDF Shipment](https://github.com/mageplaza/pdf-invoice-templates/tree/master/shipment)
* [PDF Credit Memo](https://github.com/mageplaza/pdf-invoice-templates/tree/master/creditmemo)

What makes our module prominent is that there are premade templates for store owners to use in the backend. More interestingly, those templates are flexibly customizable. Specially, Mageplaza PDF Invoice provides
* HTML support.
* CSS support.
* Available variables from the order.
* Custom variables support

Let’s take a look at those alluring templates that Mageplaza has done for you.

### PDF Invoice template
PDF Invoice files are the real savior to implement your user experiment when it comes to the instant support that your customers want to print their invoice immediately quickly and nicely. 

We’re sure you have known that Barcodes and QR codes are hi-tech trends and they’re pretty appreciated by fan of mobile devices. Boutique owners love applying this to their shopping system. Therefore, Barcode or QR code is also welcomed in this type of invoice by entering its variables in the Edit Template box.

**A sample template:**

``` html 
<!doctype html>
<html>
<body>
<div id="wrapper">
    <div class="header">
        <div class="header-left">
            <div class="logo-left">
                <a class="logo" href="{{store url=""}}">
                <img
                        width="{{var businessInformation.getLogoWidth()}}"
                        height="{{var businessInformation.getLogoHeight()}}"
                        src="{{var logo_url}}"
                        alt="{{var logo_alt}}"
                        border="0"
                />
                </a>
            </div>
            <div class="business-information">
                <p class="business-name">{{var businessInformation.getCompany()}}</p>
                <p>{{trans "Address"}}: {{var businessInformation.getAddress()}}</p>
                <p>{{trans "Phone"}}: {{var businessInformation.getPhone()}}</p>
                <p>{{trans "Tax ID"}} {{var businessInformation.getVatNumber()}}</p>
                <p>{{trans "Contact"}}: {{var businessInformation.getContact()}}</p>
                <p>{{trans "Registered"}}: {{var businessInformation.getRegistered()}}</p>
            </div>
        </div>
        <div class="header-right">
            <div class="info">
                <h1 class="info-title">{{trans "INVOICE"}}</h1>
                <p>{{trans "Invoice "}} <b>#{{var invoice.increment_id}}</b></p>
                <p>{{trans "Date : "}} <b>{{var pdfInvoiceCustom.formatDate($invoice.created_at)}}</b></p>
                <p>{{trans "Amount : "}}<b>{{var order.formatPrice($invoice.getGrandTotal())|raw }}</b></p>
                <!-- BARCODE: Sugest Type: C39/EAN128A -->
                <p class="mp-invoice-barcode">
                    <barcode code="{{var invoice.increment_id}}" type="C39"/>
                </p>
                <!-- QRCODE -->
                <!-- <p class="mp-invoice-barcode"><barcode code="{{var invoice.increment_id}}" type="QR" size="0.8" error="M" disableborder="1"  /></p> -->
                <!-- Sugest Type:-->
            </div>
        </div>
    </div>
    <div class="clr"></div>
    <div class="content">
        <div class="address">
            <div class="billing-address">
                <h3 class="mp-block-heading">{{trans "Billing Address"}}</h3>
                <p>{{var formattedBillingAddress|raw}}</p>
            </div>
            <div class="payment-method">
                <h3 class="mp-block-heading">{{trans "Payment Method"}}</h3>
                <p>{{var payment_title|raw}}</p>
            </div>
        </div>
        <div class="clr"></div>
    </div>
    {{layout handle="pdfinvoice_order_invoice_items" invoice=$invoice order=$order itemBarcode=1}}
    <footer>
        {{depend invoiceNote}}
        <div class="footer-left">
            <h3 class="mp-note">{{trans "Notes"}}:</h3>
            <span style="font-style: italic;">{{var invoiceNote|raw}}</span>
        </div>
        {{/depend}}
    </footer>
</div>
</body>
</html>
```



To see this template in the backend, go ``Mageplaza > PDF Invoices: Manage Template > Default PDF Invoice: Edit``

 ![pdfinvoice1](https://i.imgur.com/7Hqs4Fy.gif)

You can preview the template by clicking **Preview**. Here is the designed template without any modifications.

![pdfinvoice2](https://i.imgur.com/PHQUA1W.jpg)

Make sure that you’ve chosen the right template to print, go to ``Mageplaza > PDF Invoices: Configuration > Invoice``, in the **Select Template** field, choose “Default PDF Invoice”

### PDF Order template
Basically, the module will get the precise information on the order, and inform it on the PDF file without any flaws. Even if you have some custom fields on the checkout page but you have no idea if it can be printed on the PDF files, no worries, it will be. After consumers place their orders, this PDF Order file will be included in the email confirmation automatically.  

In the backend demo, make your way to ``Mageplaza > PDF Invoices: Manage Templates``. Choose **Edit** for **Default PDF Order**. The form will be displayed and now you can make any customization in designing template as you want.

 ![pdforder1](https://i.imgur.com/iXYLhdi.gif)

Here is the visual display of the Order template in the default:

![pdforder1](https://i.imgur.com/XGUwmYR.jpg)

### PDF Shipment template
No one wishes their merchandises to be lost on the way, so delivery information should be taken into account carefully at the first place. If our module can mirror accurately shipping information on the printable file? Absolutely, this ease one will be the one size fits all. You can experience its compatibility that includes both Shipping Address and Billing Address on the paper amazingly.

First, you can preview and edit the template at ``Mageplaza > PDF Invoices: Manage Template``, choose to edit the **Default PDF Shipment** file.

![pdfshipment1](https://i.imgur.com/64lp6ca.gif)

Similar to the feature in the template for PDF Invoice and PDF Order, variables for Barcode and QR code also can be accepted here. You can take this advantage to enrich more information for your invoice more than it’s supposed.

This is the available template for shipment invoices. 

![pdfshipment2](https://i.imgur.com/NLR9S1t.jpg)
 

### PDF Credit Memo template
As far as you know, a credit memo (or credit memorandum) is a special type of document that is really helpful in the accounting system. In case of not being able to receive merchandises at the best status, and instead of giving the refund back to buyers, sellers will issue a credit memo which is written the details of the order, dealt pricings or some additional notes. And this document can be used to reduce or eliminate entirely the total amount buyers have to pay off.

To configure an automatic sending credit memo, take a look at how your file will be previewed, the premade template is placed in ``Mageplaza > PDF Invoices: Manage Template > Default PDF Credit Memo``.
  
![pdfcreditmemo1](https://i.imgur.com/Yww98qO.gif)

After saving the edit for the template, you can click **Preview** to see your final result again. Then make sure you can use this by choosing it in ``Mageplaza > PDF Invoices: Configuration > Credit Memo: Select Template``.

![pdfcreditmemo2](https://i.imgur.com/p7DnC5p.jpg)


Be notice that if there is any possible updates on templates, we will update them on the Github interface instead of adding into the module’s code directly. You can bookmark this post in case you want to implement more design for templates in the PDF Invoices extension.

Again, Mageplaza always desires to deliver the best service, we want to hear your thoughts directly and regularly. The power of knowledge is sharing, we’re waiting for all your volunteer contributions of more custom templates done by your own hands. We’re looking forward to seeing how magnificent creativity our customers can have.  

