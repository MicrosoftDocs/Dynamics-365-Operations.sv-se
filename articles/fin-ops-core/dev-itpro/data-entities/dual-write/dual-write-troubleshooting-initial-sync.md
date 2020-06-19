---
title: Felsöka problem under första synkroniseringen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410091"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Felsöka problem under första synkroniseringen

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Sök efter inledande synkroniseringsfel i en Finance and Operations-app

När du har aktiverat mappningsmallen ska status för mappningarna **köras**. Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen. Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.

![Fliken Information om initial synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:

*Fjärrservern returnerade ett fel: (400) felaktig begäran.) AX, exporten upptäckte ett fel*

Här följer ett exempel på det fullständiga felmeddelandet.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.

1. Logga in på den virtuella datorn (VM) för Finance and Operations-appen.
2. Öppna Microsoft Management Console.
3. I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs. Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.

## <a name="initial-synchronization-error-403-forbidden"></a>Fel vid första synkronisering: 403 förbud

Följande felmeddelande kan visas under första synkroniseringen:

*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*

Gör så här om du vill åtgärda problemet.

1. Logga in på Finance and Operations-appen.
2. På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.

![Lista över Azure AD-appar](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Självreferens- eller cirkulära referensfel vid inledande synkronisering

Ett felmeddelande om någon av dina mappningar har självreferenser eller cirkulära referenser. Felen hör till dessa kategorier:

- [Leverantörer V2 till entitetsmappningen msdyn_vendors](#error-vendor-map)
- [Kund V3 till entitetsmappningen Konto](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Lös ett fel i leverantörerna V2 och entitetsmappningen msdyn_vendors

Du kan stöta på följande initiala synkroniseringsfel på **Leverantörer V2** till **msdyn_vendors** mappning om entiteterna har befintliga poster med värden i fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber**. Detta beror på att **InvoiceVendorAccountNumber** är ett självrefererande fält och att **PrimaryContactPersonId** är en cirkelreferens i leverantörsmappningen.

*Det gick inte att matcha GUID för fältet: <field>. Det gick inte att hitta sökningen: <value>. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Här följer några exempel:

- *Det gick inte att matcha GUID för fältet: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Det gick inte att matcha GUID för fältet: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. Det gick inte att hitta sökningen: V24-1. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Om du har poster med värden i dessa fält i leverantörsenheten följer du stegen i avsnittet nedan för att slutföra den inledande synkroniseringen.

1. I Finance and Operations-appen tar du bort fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och sparar ändringarna.

    1. Navigera till mappning med dubbelriktad skrivning för **leverantörer V2 (msdyn_vendors)** och välj fliken **enhetsmappningar**. I vänster filter väljer du **Finance and Operations apps.Vendors V2**. I höger filter, välj **Sales.Vendor**.

    2. Sök efter **primarycontactperson** för att hitta källfältet **PrimaryContactPersonId**.
    
    3. Klicka på knappen **Åtgärder** och välj **Ta bort**.
    
        ![egen eller cirkelreferens 3](media/vend_selfref3.png)
    
    4. Upprepa detta om du vill ta bort fältet **InvoiceVendorAccountNumber**.
    
        ![egen eller cirkelreferens 4](media/vend-selfref4.png)
    
    5. Spara mappningsändringarna.

2. Inaktivera ändringsspårningen för entiteten **leverantörer V2**.

    1. Navigera till **Datahantering \> Dataentiteter**.
    
    2. Välj entiteten **Leverantörer V2**.
    
    3. Klicka på **alternativ** i menyraden och sedan på **ändra spårning**.
    
        ![egen eller cirkelreferens 5](media/selfref_options.png)
    
    4. Klicka på **inaktivera ändringsspårning**.
    
        ![egen eller cirkelreferens 6](media/selfref_tracking.png)

3. Kör mappningen av den första synkroniseringen av **leverantörer v2 (msdyn_vendors)**. Den ursprungliga synkroniseringen bör köras utan fel.

4. Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**. Du måste synkronisera den här mappningen om du vill synkronisera fältet primär kontakt på leverantörsenheten eftersom kontaktposterna också måste synkroniseras.

5. Lägg till fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** tillbaka till mappningen **leverantörer V2 (msdyn_vendors)** och spara mappningen.

6. Kör den första synkroniseringen igen för mappningen **leverantörer v2 (msdyn_vendors)**. Alla poster kommer att synkroniseras eftersom spårning av ändringar har inaktiverats.

7. Aktivera ändringsspårningen för entiteten **leverantörer V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Lös ett fel i enhetsmappning för kunder V3 till konton

Du kan stöta på följande initiala synkroniseringsfel på mappningen **Kunder V3** till **Konton** om entiteterna har befintliga poster med värden i fälten **ContactPersonID** och **InvoiceAccount**. Detta beror på att **InvoiceAccount** är ett självrefererande fält och att **ContactPersonID** är en cirkelreferens i leverantörsmappningen.

*Det gick inte att matcha GUID för fältet: <field>. Det gick inte att hitta sökningen: <value>. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *Det gick inte att matcha GUID för fältet: primarycontactid.msdyn_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Det gick inte att matcha GUID för fältet: msdyn_billingaccount.accountnumber. Det gick inte att hitta sökningen: 1206-1. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Om du har poster med värden i dessa fält i kundenheten följer du stegen i avsnittet nedan för att slutföra den inledande synkroniseringen. Du kan använda den här metoden för alla enheter utanför lådan, t.ex. konton och kontakter.

1. I Finance and Operations-appen, ta bort fälten **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)**-mappningen och spara mappningen.

    1. Navigera till mappning med dubbelriktad skrivning för **Kunder V3 (konton)** och välj fliken **enhetsmappningar**. I vänster filter, välj **Finance and Operations app.Customers V3**. I höger filter, välj **Common Data Service.Account**.

    2. Sök efter **contactperson** för att hitta källfältet **ContactPersonID**.
    
    3. Klicka på knappen **Åtgärder** och välj **Ta bort**.
    
        ![egen eller cirkelreferens 3](media/cust_selfref3.png)
    
    4. Upprepa detta om du vill ta bort fältet **InvoiceAccount**.
    
        ![egen eller cirkelreferens](media/cust_selfref4.png)
    
    5. Spara mappningsändringarna.

2. Inaktivera ändringsspårningen för entiteten **kunder V3**.

    1. Navigera till **Datahantering \> Dataentiteter**.
    
    2. Välj entiteten **kunder V3**.
    
    3. Klicka på **alternativ** i menyraden och sedan på **ändra spårning**.
    
        ![egen eller cirkelreferens 5](media/selfref_options.png)
    
    4. Klicka på **inaktivera ändringsspårning**.
    
        ![egen eller cirkelreferens 6](media/selfref_tracking.png)

3. Kör den första synkroniseringen för mappningen **Kunder V3 (konton)**. Den ursprungliga synkroniseringen bör köras utan fel.

4. Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**. Det finns 2 mappningar med samma namn. Välj den som innehåller **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].** på fliken **Detaljer** på kartan.

5. Lägg till fälten **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen. Nu är både fältet **InvoiceAccount** och fältet **ContactPersonId** del i ett direkt synkroniseringsläge. I nästa steg slutför du den inledande synkroniseringen för dessa fält.

6. Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**. Eftersom ändringsspårning är inaktiverat synkroniserar körningen av synkronisering data för **InvoiceAccount** och **ContactPersonId** från Finance and Operations-appen till Common Data Service.

7. Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Common Data Service till Finance and Operations, använder du ett dataintegreringsprojekt.

    1. I Power Apps skapar du ett dataintegreringsprojekt mellan **Sales.Account** och **Finance and Operations-appar. Kunder V3**-enheter. Datariktningen måste vara från Common Data Service till Finance and Operations-appen.  Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det här attributet. Mer information finns i [integrera data i Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.

        ![egen eller cirkelreferens](media/cust_selfref6.png)

    2. Lägg till företagskriterierna i filtret på Common Data Service sidan, eftersom endast de poster som matchar filter villkoren kommer att uppdateras i  Finance and Operations-appen. Klicka på filter ikonen om du vill lägga till ett filter. I dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **_msdyn_company_value eq '\<guid\>'**. Om det inte finns någon filterikon skapar du ett supportärende som ber dataintegrationsgruppen att aktivera filterkapaciteten för din klientorganisation. Om du inte anger någon filterfråga för **_msdyn_company_value** synkroniseras alla poster.

        ![egen eller cirkelreferens](media/cust_selfref7.png)

        Detta slutför den inledande synkroniseringen av posterna.

8. Aktivera ändringsspårningen för entiteten **kunder V3** i Finance and Operations-appen.

