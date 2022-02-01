---
title: Uppgradera till part- och globala adressboksmodellen.
description: I detta ämne beskrivs hur du uppgraderar data för dubbel skrivning till parten samt till den globala adressboksmodellen..
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: eaafe8d98049cb8838317396f28e9d6ca720a677
ms.sourcegitcommit: 08dcbc85e372d4e4fb3ba64389f6d5051212c212
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2022
ms.locfileid: "8015725"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Uppgradera till part- och globala adressboksmodellen

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Mallen [Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) hjälper dig att uppgradera följande befintliga data i dubbelskrivning till party- och global adressboksmodell: data i tabellerna **Konto**, **Kontakt** och **Leverantör** samt postadresser och e-postadresser.

Följande tre Data Factory-mallar finns. De hjälper till att stämma av data från både appar för ekonomi och drift och kundengagemangsappar.

- **[Partmall](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Uppgradera data dubbelriktad skrivning Party-GAB schema/arm_template.json)** – Denna all hjälper dig att uppgradera data för **Part** och **Kontakt** som är kopplad till data för **Konto**, **Kontakt** och **Leverantör**.
- **[Partens postadressmall](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Uppgradera data dubbelriktad skrivning Party-GAB schema/Uppgradera till partens postadress - GAB/arm_template.json)** – Denna mall hjälper dig att uppgradera de postadresser som är kopplade till data för **Konto**, **Kontakt** och **Leverantör**.
- **[Partens elektroniska adressmall](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Uppgradera data dubbelriktad skrivning Party-GAB schema/Uppgradera till partens elektroniska adress - GAB/arm_template.json)** – Denna mall hjälper dig att uppgradera de elektroniska adresser som är kopplade till data för **Konto**, **Kontakt** och **Leverantör**.

I slutet av processen genereras följande kommaavgränsade värden (.csv).

| Filnamn | Syfte |
|---|---|
| FONewParty.csv | Den här filen hjälper till att skapa nya **Part** poster inne i app för ekonomi och drift. |
| ImportFONewPostalAddressLocation.csv | Den här filen hjälper till att skapa nya **Postadressplats** poster i appen för ekonomi och drift. |
| ImportFONewPartyPostalAddress.csv | Den här filen hjälper till att skapa nya **Partens postadress** poster i appen för ekonomi och drift. |
| ImportFONewPostalAddress.csv | Den här filen hjälper till att skapa nya **postadress** poster i appen för ekonomi och drift. |
| ImportFONewElectronicAddress.csv | Den här filen hjälper till att skapa nya **elektronisk adress** poster i appen för ekonomi och drift. |

I detta ämne finns instruktioner om hur du använder Data Factory-mallar och uppgraderar dina data. Om du inte har några anpassningar kan du använda mallar som de är. Men om du har anpassningar för data för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallarna som beskrivs i detta ämne.

> [!IMPORTANT]
> Det finns särskilda instruktioner om du ska köra mallen för partens postadress och den elektroniska adressen för parten. Du måste först köra partmallen, sedan mallen för partens postadress och sedan mallen för den elektroniska adressen för parten. Varje mall har utformats för import i en separat datafabrik.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar krävs för att du ska kunna uppgradera till den part och den globala adressboksmodellen:

+ Du måste ha ett [Azure-abonnemang](https://portal.azure.com/).
+ Du måste ha åtkomst till [mallarna](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Du måste vara en befintlig kund.

## <a name="prepare-for-the-upgrade"></a>Förbereda uppgraderinge

En uppgradering kräver följande förberedelser:

+ **Fullständig synkronisering:** Både Finance and Operations-miljön och kundengagemangsmiljön är i ett helt synkroniserat tillstånd för tabellerna **Konto (kund)**, **Kontakt** och **Leverantör**.
+ **Integreringsnycklar**: Registren **Konto (Kund)**, **Kontakt** och **Leverantör** i program för kundengagemang använder de integreringsnycklar. Om du anpassar integreringsnycklarna måste du anpassa mallen.
+ **Partsnummer:** Alla **Kontro (kund)**, **Kontakt** och **Leverantör** poster som ska uppgraderas har ett partsnummer. Poster som inte har något partnummer ignoreras. Om du vill uppgradera dessa poster lägger du till ett Partsnummer i dem innan du startar uppgraderingsprocessen.
+ **Systemavbrott**: Under uppgraderingen måste du ta både Finance and Operations-miljön och miljön för kundengagemangsmiljön offline.
+ **Ögonblicksbild:** Ta ögonblicksbilder av både appen för ekonomi och drift och appen för kundengagemang. Du kan sedan använda ögonblicksbilderna om du vill återställa föregående status.

## <a name="deployment"></a>Distribution

1. Hämta mallarna från [Implementeringstillgångar för Dynamics-365-FastTrack](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Logga in på [Azure-portal](https://portal.azure.com/).
3. Skapa en [resursgrupp](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Skapa ett [lagringskonto](/azure/storage/common/storage-account-create?tabs=azure-portal) i resursgruppen som du skapade.
5. Skapa en [datafabrik](/azure/data-factory/quickstart-create-data-factory-portal) i resursgruppen som du skapade.
6. Öppna datafabriken och välj panelen **Skapa och övervaka**.
7. På fliken **Hantera** väljer du **ARM-mall**.
8. Välj **Importera ARM-mall** för att importera mallen **Part**.
9. Importera mallen till datafabriken. Ange följande värden för **Projektinformation** och **Instansinformation**.

    | Fält | Värde |
    |---|---|
    | Abonnemang | Azure-abonnemang |
    | Resursgrupp | Ange samma resurs under vilken lagringskontot skapas under. |
    | Region | Region |
    | Fabriksnamn | Fabriksnamn |
    | Huvudservicenyckel för kopplad FO-service | Nyckeln för ansökan |
    | Anslutningssträng för Azure Blob Storage | Anslutningssträng för Azure Blob Storage |
    | Kopplat tjänstelösenord för Dynamics Crm | Lösenordet för det användarkonto du angett som användarnamn. |
    | FO Linked Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO Linked Service_properties_type Properties_tenant | Information om klientorganisation (domännamn eller ID för klientorganisation) som programmet finns under |
    | FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO Linked Service_properties_type Properties_service Principal Id | Programmets klient-ID |
    | Dynamics Crm Linked Service_properties_type Properties_username | Användarnamnet som används för att koppla till Dynamics 365 |

    Mer information finns i följande avsnitt:

    - [Manuellt främja en Resource Manager-mall för varje miljö](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Länkade tjänsteegenskaper](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Kopiera data med Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Efter distributionen kan du validera datauppsättningarna, dataflödet och länkad tjänst för datafabriken.

    ![Datauppsättningar, dataflöde och länkad tjänst.](media/data-factory-validate.png)

11. Gå till **Hantera**. Under **Anslutningar** väljer du **Kopplad tjänst**. Välj **DynamicsCrmLinkedService**. Ange följande värden i dialogrutan **Redigera kopplad tjänst (Dynamics CRM)**.

    | Fält | Värde |
    |---|---|
    | Namn | DynamicsCrmLinkedService |
    | beskrivning | Kopplade tjänster för anslutning med CRM-instans för hämtning av entitetsdata |
    | Anslut via integreringskörning | AutoResolvelntegrationRuntime |
    | Distributionstyp | Online |
    | Service-Uri | `https://<organization-name>.crm[x].dynamics.com` |
    | Autentiseringstyp | Office365 |
    | Användarnamn | |
    | Lösenord eller Azure-nyckelvalv | Lösenord |
    | Lösenord | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Förbereda körning av mallar för Data Factory

I det här avsnittet beskrivs de inställningar som krävs för att du ska kunna köra mallarna för partens postadress och den elektroniska partens adress Data Factory-mallar.

### <a name="setup-to-run-the-party-postal-address-template"></a>Inställningar för att köra mallen för partens postadress

1. Logga in på apparna för kundrelationer och gå till **Inställningar** \> **Anpassade inställningar**. På fliken **Allmänt**, konfigurera tidszonsinställning för systemadministratörskontot. Tidszonen måste finnas i UTC (Coordinated Universal Time) för att det ska gå att uppdatera datumen "giltigt från" och "giltig till" för postadresser från Ekonomi och Drift-appar.

    ![Tidszoninställning för systemets admininstrationskonto.](media/ADF-1.png)

2. I Data Factory, på fliken **Hantera** under **Globala parametrar**, skapa följande global parameter.

    | Nummer | Namn | Typ | Värde |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | sträng | Den här parametern lägger till ett serienummer till nya postadresser som prefix. Se till att tillhandahålla en sträng som inte står i konflikt med postadresser i Ekonomi och Drift-appar och kundengagemangsappar. Använd till exempel **ADF-PAD-**. |

    ![Global parametern PostalAddressIdPrefix som skapats på fliken Hantera.](media/ADF-2.png)

3. Välj **Publicera alla** när du är klar.

    ![Knappen Publicera alla.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Inställningar för att köra mallen för partens elektroniska adress

1. I Data Factory, på fliken **Hantera** under **Globala parametrar**, skapa följande globala parametrar.

    | Nummer | Namn | Typ | Värde |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Denna parameter bestämmer vilka primära systemadresser som ersätts vid konflikter. Om värdet är **sant** ersätter de primära adresserna i appar för ekonomi och drift de primära adresserna i kundengagemangsappar. Om värdet är **falsk** ersätter de primära adresserna i kundengagemangsappar de primära adresserna i appar för ekonomi och drift. |
    | 2 | ElectronicAddressIdPrefix | sträng | Den här parametern lägger till ett serienummer till nya elektroniska adresser som prefix. Se till att tillhandahålla en sträng som inte står i konflikt med elektroniska adresser i Ekonomi och Drift-appar och kundengagemangsappar. Använd till exempel **ADF-EAD-**. |

    ![IsFOSource och ElectronicAddressIdPrefix globala parametrar skapade på fliken Hantera.](media/ADF-4.png)

2. Välj **Publicera alla** när du är klar.

## <a name="run-the-templates"></a>Kör mallar

1. Stoppa följande dubbelriktade mappningar för **Konto**, **Kontakt** och **Leverantör** med hjälp av appen för ekonomi och drift:

    + Kunder V3 (konton)
    + Kunder V3 (kontakter)
    + CDS-kontakter V2 (kontakter)
    + CDS-kontakter V2 (kontakter)
    + Leverantör V2 (msdyn_vendor)

2. Kontrollera att kartorna har tagits bort från **msdy_dualwriteruntimeconfig** registret i Dataverse.
3. Installera [lösningar för dubbel skrivningspart och global adressbok](https://aka.ms/dual-write-gab) från AppSource.
4. I appen för ekonomi och drift, kör **Initial synkronisering** för följande tabeller om de innehåller data:

    + Tilltal
    + Typer av personliga egenskaper
    + Avslutningsfras
    + Kontaktpersonens titlar
    + Roller för beslutsfattare
    + Lojalitetsnivåer

5. Inaktivera följande instickssteg i programmet för kundengagemang:

    + Kontouppdatering

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering

    + Kontaktuppdatering

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering

    + Uppdatering av msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party

    + Uppdatering av msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor

    + Customeraddress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: Skapa customeraddress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: Uppdatering av customeraddress

        + Delete

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: Ta bort customeraddress

    + msdyn_partypostaladdress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: Skapa msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: Skapa msdyn_partypostaladdress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: Uppdatera msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: Uppdatera msdyn_partypostaladdress

    + msdyn_postaladdress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: Skapa msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: Skapa msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: Skapa msdyn_postaladdress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: Uppdatera msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: Uppdatera msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: Skapa msdyn_partyelectronicaddress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: Uppdatera msdyn_partyelectronicaddress

        + Delete

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: Ta bort msdyn_partyelectronicaddress

6. Inaktivera följande arbetsflöden i programmet för kundengagemang:

    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer av typen "person" i registret Kontakter
    + Skapa leverantörer av typen person i tabellen Leverantörer
    + Uppdatera leverantörer i tabellen Konton
    + Uppdatera leverantörer i tabellen Leverantörer
    + Uppdatera leverantörer av typen person i tabellen Kontakter
    + Uppdatera leverantörer av typen person i tabellen Leverantörer

7. Kör mallen i datafabriken genom att välja **Utlösa nu** på det sätt som visas i bilden nedan. Denna process kan ta några timmar att slutföra baserat på datavolymen.

    ![Köra mallen.](media/data-factory-trigger.png)

    > [!NOTE]
    > Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen.

8. Importera de nya **Part**-posterna i appen för ekonomi och drift.

    1. Hämta filen **FONewParty.csv** fil från Azure Blob storage. Sökvägen är **partybootstrapping/output/FONewParty.csv**.
    2. Konvertera filen **FONewParty.csv** till en Excel-fil och importera Excel-filen till app för ekonomi och drift. Alternativt, om CSV-importen fungerar kan du importera .csv-filen direkt. Detta steg kan ta några timmar att slutföra baserat på datavolymen. Mer information finns i [Översikt över dataimport- och exportjobb](../data-import-export-job.md).

    ![Importera Dataverse partsposter.](media/data-factory-import-party.png)

9. I datafabriken kör du mallarna för partens postadress och partens elektroniska adress, en efter en.

    + Partens postadressmall upsert alla postadressposter i kundengagemangsappen och associerar dem med motsvarande **Konto**, **Kontakt** och **Leverantör**. Det genererar också tre .csv-filer: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv och ImportFONewPostalAddress.csv.
    + Partens elektroniska postadressmall upsert alla elektroniska postadressposter i kundengagemangsappen och associerar dem med motsvarande **Konto**, **Kontakt** och **Leverantör**. Den genererar också en .cvs-fil: ImportFONewElectronicAddress.csv.

    ![Köra mallarna för partens postadress och den elektroniska adressen till parten.](media/ADF-7.png)

10. Om du vill uppdatera appen för ekonomi och drift med denna data måste du konvertera .csv-filer till en Excel-arbetsbok och [importera den till app för ekonomi och drift](/data-entities/data-import-export-job). Alternativt, om CSV-importen fungerar kan du importera .csv-filer direkt. Detta steg kan ta några timmar att slutföra baserat på volymen.

    ![Import klar.](media/ADF-8.png)

11. Aktivera följande instickssteg i programmet för kundengagemang:

    + Kontouppdatering

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering

    + Kontaktuppdatering

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering

    + Uppdatering av msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party

    + Uppdatering av msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor

    + msdyn_partypostaladdress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: Skapa msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: Skapa msdyn_partypostaladdress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: Uppdatera msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: Uppdatera msdyn_partypostaladdress

    + msdyn_postaladdress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: Skapa msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: Skapa msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: Skapa msdyn_postaladdress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: Uppdatera msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: Uppdatera msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Skapa

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: Skapa msdyn_partyelectronicaddress

        + Uppdatera

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: Uppdatera msdyn_partyelectronicaddress

        + Delete

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: Ta bort msdyn_partyelectronicaddress

12. Aktivera följande arbetsflöden i kundkopplingsprogrammen om du inaktiverat tidigare:

    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer av typen "person" i registret Kontakter
    + Skapa leverantörer av typen person i tabellen Leverantörer
    + Uppdatera leverantörer i tabellen Konton
    + Uppdatera leverantörer i tabellen Leverantörer
    + Uppdatera leverantörer av typen person i tabellen Kontakter
    + Uppdatera leverantörer av typen person i tabellen Leverantörer

13. Kör de **part**-postrelaterade kartorna enligt instruktionerna i [Part och global adressbok](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Förklaring av mallarna för Data Factory-mallar

I det här avsnittet går du igenom stegen i varje Data Factory-mall.

### <a name="steps-in-the-party-template"></a>Steg i partsmallen

1. Steg 1 till 6 identifierar företagen som är aktiverade för dubbelriktad skrivning och skapar en filterklausul för dem.
2. Steg 7-1 till 7-9 hämtar data från både appen för ekonomi och drift och kundengagemangsappen som data ska uppgraderas till.
3. I steg 8 till 9 jämförs partsnumret för posterna **Konto**, **Kontakt** och **Leverantör** mellan app för ekonomi och drift och kundengagemangsapp. Eventuella poster som inte har något partnummer hoppas över.
4. Steg 10 genererar två CSV-fil för partsposterna som måste skapas i kundengagemangsappen för app för ekonomi och drift.

    - **FOCDSParty.csv** – Den här filen innehåller alla partposter för båda systemen, oavsett om företaget är aktiverat för dubbelriktad skrivning.
    - **FONewParty.csv** – Den här filen innehåller en delmängd av partposterna som Dataverse är medveten om (till exempel konton av typen **Potentiell kund**).

5. Steg 11 skapar parterna i kundengagemangsappen.
6. Steg 12 hämtar parternas globalt unika identifierare (GUID) från kundengagemangsappen och arrangerar dem så att de kan associeras med poster **Konto**, **Kontakt** och **Leverantör** i efterföljande steg.
7. Steg 13 associerar posterna **Konto**, **Kontakt** och **Leverantör** med part-GUID.
8. Steg 14-1 till 14-3 uppdaterar posterna **konto**, **kontakt** och **leverantör** i kundengagemangsappen med part-GUID.
9. Steg 15-1 till 15-3 förbereder posten **Kontakt för part** för posterna **konto**, **kontakt** och **leverantör**.
10. Steg 16-1 till 16-7 hämtar referensdata, till exempel tilltals- och personliga egenskaper och kopplar den till posten **Kontakt för part**.
11. Steg 17 sammanfogar posterna **Kontakt för part** för posterna **konto**, **kontakt** och **leverantör**.
12. I steg 18 importeras **kontakt för part**-poster till kundengagemangsappen.

### <a name="steps-in-the-party-postal-address-template"></a>Steg i mallen för partens postadress

1. Steg 1-1 till 1-10 hämtar data från både appen för ekonomi och drift och kundengagemangsappen som data ska uppgraderas till.
2. Steg 2 avnormaliserar postadressdata i appen för ekonomi och drift genom att sammanfoga postadressen och partens postadress.
3. Steg 3 deduplicerar och slår samman konto-, kontakt- och leverantörsadressdata från kundengagemangsappen.
4. Steg 4 skapar .csv-filer för app för ekonomi och drift för att skapa ny adressdata som är baserad på konto-, kontakt- och leverantörsadresser.
5. Steg 5-1 skapar .cvs-filer för kundengagemangsappen för att skapa alla adressdata baserat på både app för ekonomi och drift och kundengagemangsappen.
6. I steg 5-2 konverteras .cvs-filerna till Ekonomi och Drift importformatet för manuell import.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. Steg 6 importerar insamlingsdata för postadresser till kundengagemangsappen.
8. Steg 7 hämtar insamlingsdata för postadresser från kundengagemangsappen.
9. I steg 8 skapas kundadressdata och associerar med ett samlings-ID för postadressen.
10. Steg 9-1 till 9-2 kopplar insamlings-ID:n för part och postadress med postadresser och partiadresser.
11. Steg 10-1 till 10-3 importerar kundadresser, postadresser och partens postadresser till kundengagemangsappen.

### <a name="steps-in-the-party-electronic-address-template"></a>Steg i mallen för partens elektroniska postadress

1. Steg 1-1 till 1-5 hämtar data från både appen för ekonomi och drift och kundengagemangsappen som data ska uppgraderas till.
2. Steg 2 konsoliderar elektroniska adresser i kundengagemangsappen från konto-, kontakt- och leverantörsenheter.
3. Steg 3 sammanfogar primära elektroniska adressdata från kundengagemangsappen och appen för ekonomi och drift.
4. Steg 4 skapar .csv-filer.

    - Skapa nya elektroniska adressdata för appen för ekonomi och drift, baserat på konto-, kontakt- och leverantörsadresser.
    - Skapa nya elektroniska adressdata för kundengagemangsappen, baserat på elektronisk adress, konto, kontakt- och leverantörsadresser i appen för ekonomi och drift.

5. I steg 5-1 importeras elektroniska adresser till kundengagemangsappen.
6. Steg 5-2 skapar .cvs-filer för att uppdatera primära adresser för konton och kontakter i kundengagemangsappen.
7. Steg 6–1 till 6–2 importerar konton och primära adresser till kundengagemangsappen.

## <a name="troubleshooting"></a>Felsökning

1. Om processen misslyckas kör du om datafabriken. Starta från den misslyckade aktiviteten.
2. Vissa filer genereras av den datafabrik som du kan använda för datavalidering.
3. Datafabriken körs baserat på .csv-filer. Om ett kommatecken ingår i något fältvärde kan det därför störa resultaten. Du måste ta bort alla kommatecken från fältvärdena.
4. På fliken **Övervakning** finns information om alla steg och data som bearbetas. Välj ett specifikt steg för att felsöka det.

    ![Fliken Övervakning.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Läs mer om mallen

Mer information om mallen finns i [Kommentarer för Azure Data Factory-mallen readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
