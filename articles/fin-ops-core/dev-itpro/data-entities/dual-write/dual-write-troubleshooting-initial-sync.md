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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: a2f0e0cbf0f8710dc020a48506775fa28df9c2d2
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744647"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Felsöka problem under första synkroniseringen

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse. Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Sök efter inledande synkroniseringsfel i en Finance and Operations-app

När du har aktiverat mappningsmallen ska status för mappningarna **köras**. Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen. Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.

![Fel på fliken information om inledande synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:

*(\[Felaktig begäran\], Fjärrservern returnerade ett fel: (400) felaktig begäran.), AX exporten upptäckte ett fel*

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

![DtAppID-klient i listan över Azure AD-program](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Självreferens- eller cirkulära referensfel vid inledande synkronisering

Ett felmeddelande om någon av dina mappningar har självreferenser eller cirkulära referenser. Felen hör till dessa kategorier:

- [Fel i tabellmappning för Leverantörer V2 till msdyn_vendors](#error-vendor-map)
- [Fel i tabellmappning för kunder V3 till konton](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Lös fel i tabellmappning för Leverantörer V2 till msdyn_vendors

Du kan stöta på initiala synkroniseringsfel för mappning **Leverantörer V2** till **msdyn\_vendors** om tabellerna har befintliga rader med värden i kolumnerna **PrimaryContactPersonId** och **InvoiceVendorAccountNumber**. Dessa fel beror på att **InvoiceVendorAccountNumber** är ett självrefererande kolumn och att **PrimaryContactPersonId** är en cirkelreferens i leverantörsmappningen.

Felmeddelandena som visas kommer att ha följande format.

*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Nedan följer några exempel:

- *Det gick inte att matcha GUID för fältet: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Det gick inte att matcha GUID för fältet: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Det gick inte att hitta sökningen: V24-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Om några rader i leverantörstabellen har värden i kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** ska du följa dessa steg slutföra den inledande synkroniseringen.

1. I Finance and Operations-appen tar du bort kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och s för att spara ändringarna.

    1. På sidan för mappning med dubbelriktad skrivning för **Leverantörer V2 (msdyn\_vendors)** på fliken **Tabellmappningar** väljer du **Finance and Operations apps.Vendors V2**. I höger filter, välj **Sales.Vendor**.
    2. Sök efter **primarycontactperson** för att hitta källkolumen **PrimaryContactPersonId**.
    3. Välj **åtgärder** och välj sedan **ta bort**.

        ![Ta bort kolumnen PrimaryContactPersonId](media/vend_selfref3.png)

    4. Upprepa dessa steg om du vill ta bort kolumnen **InvoiceVendorAccountNumber**.

        ![Ta bort kolumnen InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. Spara dina ändringar i mappningen.

2. Inaktivera ändringsspårningen för tabellen **leverantörer V2**.

    1. I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.
    2. Välj tabellen **Leverantörer V2**.
    3. I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. Klicka på **inaktivera ändringsspårning**.

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**. Den ursprungliga synkroniseringen bör köras utan fel.
4. Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**. Du måste synkronisera den här mappningen om du vill synkronisera primära kontaktkolumnen på leverantörstabellen, eftersom initial synkronisering också måste göras för kontaktraderna.
5. Lägg till kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** tillbaka till mappningen **leverantörer V2 (msdyn\_vendors)** och spara mappningen.
6. Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**. Alla rader kommer att synkroniseras eftersom spårning av ändringar har inaktiverats.
7. Aktivera tillbaka ändringsspårningen för tabellen **leverantörer V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Lös fel i tabellmappning för Kunder V3 till konton

Du kan stöta på initiala synkroniseringsfel för mappning av **Kunder V3** till **Konton** om kolumner har befintliga rader med värden i fälten **ContactPersonID** och **InvoiceAccount**. Dessa fel beror på att **InvoiceAccount** är ett självrefererande kolumnen och att **ContactPersonID** är en cirkelreferens i leverantörsmappningen.

Felmeddelandena som visas kommer att ha följande format.

*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Nedan följer några exempel:

- *Det gick inte att matcha GUID för fältet: primarycontactid.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Det gick inte att matcha GUID för fältet: msdyn\_billingaccount.accountnumber. Det gick inte att hitta sökningen: 1206-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Om några rader i kundtabellen har värden i kolumner **ContactPersonID** och **InvoiceAccount** ska du följa dessa steg för att slutföra den inledande synkroniseringen. Du kan använda den här metoden för alla tabeller utanför lådan, t.ex. **Konton** och **Kontakter**.

1. I Finance and Operations-appen, ta bort kolumner **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)**-mappningen och spara mappningen.

    1. Navigera till sidan för mappning med dubbelriktad skrivning för **Kunder V3 (konton)** och välj fliken **Tabellmappningar** i vänster filter och välj **Finance and Operations app.Customers V3**. I höger filter, välj **Dataverse.Account**.
    2. Sök efter **contactperson** för att hitta källkolumnen **ContactPersonID**.
    3. Välj **åtgärder** och välj sedan **ta bort**.

        ![Ta bort kolumnen ContactPersonID](media/cust_selfref3.png)

    4. Upprepa dessa steg om du vill ta bort kolumnen **InvoiceAccount**.

        ![Ta bort kolumnen InvoiceAccount](media/cust_selfref4.png)

    5. Spara dina ändringar i mappningen.

2. Inaktivera ändringsspårningen för tabellen **Kunder V3**.

    1. I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.
    2. Välj tabellen **kunder V3**.
    3. I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. Klicka på **inaktivera ändringsspårning**.

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**. Den ursprungliga synkroniseringen bör köras utan fel.
4. Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.

    > [!NOTE]
    > Det finns två mappningar med samma namn. Se till att kartan som har följande beskrivning flik **Detaljer**: **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].**

5. Lägg till kolumner **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen. Nu är både kolumnen **InvoiceAccount** och kolumnen **ContactPersonId** del i ett direkt synkroniseringsläge. I nästa steg slutför du den inledande synkroniseringen för dessa kolumner.
6. Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**. Eftersom ändringsspårning är inaktiverat kommer data för **InvoiceAccount** och **ContactPersonId** att synkroniseras från Finance and Operations-appen till Dataverse.
7. Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Dataverse till Finance and Operations-appen måste du använda ett dataintegreringsprojekt.

    1. I Power Apps skapar du ett dataintegreringsprojekt mellan **Sales.Account** och **Finance and Operations-appar. Kunder V3**-tabeller. Datariktningen måste vara från Dataverse till Finance and Operations-appen. Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det. Mer information finns i [integrera data i Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).

        Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.

        ![Dataintegrationsprojekt för att uppdatera CustomerAccount och ContactPersonId](media/cust_selfref6.png)

    2. Lägg till företagskriterierna i filtret på Dataverse-sidan, eftersom endast de poster som matchar filtervillkoren kommer att uppdateras i Finance and Operations-appen. Klicka på filterknappen om du vill lägga till ett filter. Sedan i dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [OBS] Om det inte finns någon filterknapp skapar du ett supportärende som ber dataintegrationsgruppen att aktivera filterkapaciteten för din klientorganisation.

        Om du inte anger någon filterfråga för **\_msdyn\_company\_value**, synkroniseras alla rader.

        ![Lägga till en filterfråga](media/cust_selfref7.png)

    Den inledande synkroniseringen av raderna har nu slutförts.

8. I Finance and Operations-appen, aktivera tillbaka ändringsspårning på tabellen **Kunder V3**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]