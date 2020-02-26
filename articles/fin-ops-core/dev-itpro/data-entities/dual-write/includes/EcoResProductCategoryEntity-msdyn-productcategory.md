## <a name="product-categories-to-msdyn_productcategories"></a>Produktkategorier till msdyn_productcategories

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
PRODUCTCATEGORYHIERARCHYNAME | = | msdyn_hierarchy.msdyn_name | 
ISCATEGORYINHERITINGPARENTPRODUCTATTRIBUTES | >< | msdyn_isinheritingparentproductattributes | 
PROJECTCATEGORYNAME | = | msdyn_projectcategoryname | 
ISTANGIBLEPRODUCT | >< | msdyn_istangibleproduct | 
ISCATEGORYINHERITINGPARENTCATEGORYATTRIBUTES | >< | msdyn_isinheritingparentcategoryattributes | 
CATEGORYCODE | = | msdyn_code | 
CATEGORYDESCRIPTION | = | msdyn_description | 
CATEGORYKEYWORDS | = | msdyn_keywords | 
CATEGORYNAME | = | msdyn_name | 
FRIENDLYCATEGORYNAME | = | msdyn_friendlycategoryname | 
PARENTPRODUCTCATEGORYNAME | = | msdyn_parentproductcategory.msdyn_name | 
PRODUCTCATEGORYHIERARCHYNAME | >> | msdyn_parentproductcategory.msdyn_hierarchy.msdyn_name | 
