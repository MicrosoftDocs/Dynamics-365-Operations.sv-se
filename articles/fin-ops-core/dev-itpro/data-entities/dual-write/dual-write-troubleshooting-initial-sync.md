---
title: Felsöka problem under första synkroniseringen
description: Den här artikeln innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
ms.date: 06/24/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f8fb27a6af2962be31288a3d2260110e5fe6a201
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112095"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Felsöka problem under första synkroniseringen

[!include [banner](../../includes/banner.md)]



Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Söka efter initiala synkroniseringsfel i appar för ekonomi och drift

När du har aktiverat mappningsmallen ska status för mappningarna **köras**. Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen. Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.

![Fel på fliken Information om inledande synkronisering.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:

*(\[Felaktig begäran\], Fjärrservern returnerade ett fel: (400) Felaktig begäran.), AX-exporten upptäckte ett fel.*

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

1. Logga in på den virtuella datorn (VM) för appen för ekonomi och drift.
2. Öppna Microsoft Management Console.
3. I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs. Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.

## <a name="initial-synchronization-error-403-forbidden"></a>Fel vid första synkronisering: 403 förbud

Följande felmeddelande kan visas under första synkroniseringen:

*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*

Gör så här om du vill åtgärda problemet.

1. Logga in på appen för ekonomi och drift.
2. På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.

![DtAppID-klient i listan över Azure AD-program.](media/aad_applications.png)

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

1. I appen för ekonomi och drift, ta bort kolumnerna **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och spara sedan mappningen.

    1. På sidan för mappning med dubbelriktad skrivning för **Vendors V2 (msdyn\_vendors)**, på fliken **Tabellmappningar**, väljer du i det vänstra fältet **Appar för ekonomi och drift.Leverantörer V2**. I höger filter, välj **Sales.Vendor**.
    2. Sök efter **primarycontactperson** för att hitta källkolumen **PrimaryContactPersonId**.
    3. Välj **åtgärder** och välj sedan **ta bort**.

        ![Ta bort kolumnen PrimaryContactPersonId.](media/vend_selfref3.png)

    4. Upprepa dessa steg om du vill ta bort kolumnen **InvoiceVendorAccountNumber**.

        ![Ta bort kolumnen InvoiceVendorAccountNumber.](media/vend-selfref4.png)

    5. Spara dina ändringar i mappningen.

2. Inaktivera ändringsspårningen för tabellen **leverantörer V2**.

    1. I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.
    2. Välj tabellen **Leverantörer V2**.
    3. I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.

        ![Välja alternativet Ändringsspårning.](media/selfref_options.png)

    4. Klicka på **inaktivera ändringsspårning**.

        ![Klicka på Inaktivera ändringsspårning.](media/selfref_tracking.png)

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

1. I appen för ekonomi och drift tar du bort kolumnerna **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)**-mappningen och sparar sedan mappningen.

    1. På sidan för mappning med dubbelriktad skrivning för **Kunder V3 (konton)**, på fliken **Tabellmappningar**, väljer du **appen för ekonomi och drift.Kunder V3** i det vänstra filtret. I höger filter, välj **Dataverse.Account**.
    2. Sök efter **contactperson** för att hitta källkolumnen **ContactPersonID**.
    3. Välj **åtgärder** och välj sedan **ta bort**.

        ![Ta bort kolumnen ContactPersonID.](media/cust_selfref3.png)

    4. Upprepa dessa steg om du vill ta bort kolumnen **InvoiceAccount**.

        ![Ta bort kolumnen InvoiceAccount.](media/cust_selfref4.png)

    5. Spara dina ändringar i mappningen.

2. Inaktivera ändringsspårningen för tabellen **Kunder V3**.

    1. I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.
    2. Välj tabellen **kunder V3**.
    3. I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.

        ![Välja alternativet Ändringsspårning.](media/selfref_options.png)

    4. Klicka på **inaktivera ändringsspårning**.

        ![Klicka på Inaktivera ändringsspårning.](media/selfref_tracking.png)

3. Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**. Den ursprungliga synkroniseringen bör köras utan fel.
4. Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.

    > [!NOTE]
    > Det finns två mappningar med samma namn. Se till att mappningen som har följande beskrivning flik **Detaljer**: **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].**

5. Lägg till kolumner **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen. Nu är både kolumnen **InvoiceAccount** och kolumnen **ContactPersonId** del i ett direkt synkroniseringsläge. I nästa steg slutför du den inledande synkroniseringen för dessa kolumner.
6. Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**. Eftersom ändringsspårning är inaktiverat kommer data för **InvoiceAccount** och **ContactPersonId** att synkroniseras från appen för ekonomi och drift till Dataverse.
7. Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Dataverse appen för ekonomi och drift måste du använda ett dataintegreringsprojekt.

    1. I Power Apps skapar du ett dataintegreringsprojekt mellan tabellerna **Sales.Account** och **appar för ekonomi och drift.Kunder V3**. Datariktningen måste vara från Dataverse till appen för ekonomi och drift. Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det. Mer information finns i [integrera data i Dataverse](/power-platform/admin/data-integrator).

        Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.

        ![Dataintegreringsprojekt för att uppdatera CustomerAccount och ContactPersonId.](media/cust_selfref6.png)

    2. Lägg till företagskriterierna i filtret på Dataverse-sidan så att endast de poster som matchar filtervillkoren kommer att uppdateras i appen för ekonomi och drift. Klicka på filterknappen om du vill lägga till ett filter. Sedan i dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **\_msdyn\_company\_value eq '\<guid\>'**.

        > [OBS] Om det inte finns någon filterknapp skapar du ett supportärende som ber dataintegreringsgruppen att aktivera filterkapaciteten för din klientorganisation.

        Om du inte anger någon filterfråga för **\_msdyn\_company\_value**, synkroniseras alla rader.

        ![Lägga till en filterfråga.](media/cust_selfref7.png)

    Den inledande synkroniseringen av raderna har nu slutförts.

8. I appen för ekonomi och drift återaktiverar du ändringsspårning på tabellen **Kunder V3**.

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>Inledande synkroniseringsfel på mappningar med fler än 10 sökfält

Du kan komma att erhålla följande felmeddelande om du försöker köra en första synkronisering på mappningarna **Kunder V3 – Konton**, **Försäljningsorder** eller någon annan mappning med mer än 10 sökfält:

*CRMExport: Paketkörningen slutförd. Felbeskrivning 5 Försök att få data från https://xxxxx//datasets/yyyyy/tables/accounts/items?$select=kontonummer, address2_city, address2_country, ... (msdyn_company/cdm_companyid eq 'id')&$orderby=kontonummer asc misslyckades.*

På grund av sökbegränsningen för frågan misslyckas den initiala synkroniseringen när enhetsmappningen innehåller fler än 10 sökningar. Mer information finns i [Hämta relaterade tabellposter med en fråga](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query).

Följ dessa steg om du vill åtgärda problemet:

1. Ta bort valfria sökfält från enhetsmappningen för dubbel skrivning så att antalet sökfält blir 10 eller färre.
2. Spara mappningen och utför den inledande synkroniseringen.
3. När den första synkroniseringen för det första steget lyckas, lägger du till de återstående sökfälten och tar bort de sökfält som du synkroniserade i det första steget. Kontrollera att antalet sökfält är 10 eller färre. Spara mappningen och kör den inledande synkroniseringen.
4. Upprepa de här stegen tills alla sökfält är synkroniserade.
5. Lägg till alla sökfält igen på mappningen, spara mappningen och kör mappningen med **Hoppa över ursprunglig synkronisering**.

Med hjälp av den här processen kan mappningen synkroniseras i realtid.

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>Kända problem vid en första synkronisering av partens postadresser och partens elektroniska adresser

Du kan komma att få följande felmeddelande när du försöker köra den inledande synkroniseringen på partens postadresser och partens elektroniska adresser:

*Det gick inte att hitta partnumret i Dataverse.*

Det finns en intervalluppsättning för **DirPartyCDSEntity** i appar för ekonomi och drift som filtrerar parter av typen **Person** och **Organisation**. Det innebär att en första synkronisering av mappningen **CDS-parter – msdyn_parties** inte kommer att synkronisera andra typer av parter, omklusive **Juridisk person** och **Driftenhet**. När den första synkroniseringen körs för **Postadresser för CDS-part (msdyn_partypostaladdresses)** eller **Partkontakter V3 (msdyn_partyelectronicaddresses)** kan du komma att få felmeddelandet.

Vi arbetar på en korrigering för att ta bort parttypsintervallet för entiteten för ekonomi och drift så att parter av alla typer kan synkroniseras med Dataverse.

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>Finns det några prestandaproblem när man kör den första synkroniseringen av kunder eller kontaktdata?

Om du har kört den första synkroniseringen för **Kund**-data, kör **Kund**-mappningarna och sedan kör den första synkroniseringen för **Kontakter**-data kan prestandaproblem uppstå i samband med infoganden och uppdateringar av tabellerna **LogisticsPostalAddress** och **LogisticsElectronicAddress** för **Kontakt**-adresser. Samma globala postadress och elektroniska adresstabeller spåras för **CustCustomerV3Entity** och **VendVendorV2Entity** och den dubbla skrivningen försöker skapa fler frågor i syfte att skriva data till den andra sidan. Om du redan kör den första synkroniseringen för **Kund** stannar du tillhörande mappning i samband med att du kör den första synkroniseringen för **Kontakt**-data. Gör detsamma för **leverantörsdata**. När den första synkroniseringen är klar kan du köra alla mappningar genom att hoppa över den första synkroniseringen.

## <a name="float-data-type-that-has-a-zero-value-cant-be-synchronized"></a>Datatypen Flyttal som har ett nollvärde kan inte synkroniseras

Den ursprungliga synkroniseringen kan misslyckas för poster som har ett nollvärde för ett prisfält, till exempel **Fast betalningsbelopp** eller **Belopp** i transaktionsvalutan. I ett sådant fall får du ett felmeddelande som liknar följande exempel:

*Ett fel uppstod vid validering av indataparametrar: Microsoft.OData.ODataException: Det går inte att konvertera uttrycket "000000" till den förväntade typen "Edm. Decimal",...*

Problemet beror på värdet **Språk** under **Källdataformat** i modulen **Datahantering**. Ändra värdet för fältet **Språk** till **en-us** och försök sedan igen.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

