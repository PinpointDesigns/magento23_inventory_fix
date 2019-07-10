# magento23_inventory_fix

There is an issue with Magento MSI (bundled in Magento 2.3.x)
https://github.com/magento/inventory which causes a large
lag when checking stock levels for products with a
large number of child products.

Referenced here:
* https://github.com/magento/magento2/issues/22027

This is caused by a lack of keys on a newly introduced MySQL
view that has been implemented for this.

There is a fix being worked on (branched within
github against the MSI repository), but we wanted to create
a patch for this now.

Installation of this patch has been tested with `cweagans/composer-patches`
and can be installed with the following syntax: 

```
"magento/module-inventory-indexer": {
    "patch-msi-1921-performance": "patches/patch-msi-1921-performance.patch"
}
```