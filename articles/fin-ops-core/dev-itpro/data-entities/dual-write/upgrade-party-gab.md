---
title: Uppgradera till part- och globala adressboksmodellen.
description: I detta ämne beskrivs hur du uppgraderar data för dubbel skrivning till parten samt till den globala adressboksmodellen..
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95472a00d34ba939ac89b4e2484f34d50bee3088
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018322"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Uppgradera till part- och globala adressboksmodellen.

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Mallen [Azure Data Factory](https://aka.ms/dual-write-gab-adf) hjälper dig att uppgradera befintliga registerdata för dubbel skrivning för **Konto**, **Kontakt** och **Leverantör** till parten samt till den globala adressboksmodellen. I mallen stäms data från både Finance and Operations-program och program för kundrelationer av. I slutet av processen skapas fälten **Part** och **Kontakt** för **Part**-poster, som sedan associeras med poster för **Konto**, **Kontakt** och **Leverantör** i program för kundengagemang. En .csv-fil ( `FONewParty.csv`) genereras för att skapa nya **Part**-poster inuti Finance and Operations-programmet. I detta ämne finns instruktioner om hur du använder Data Factory-mallen och uppgraderar dina data.

Om du inte har några anpassningar kan du använda mallen som den är. Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen med hjälp av följande instruktioner.

> [!Note]
> Mallen underlättar uppgraderingen av endast **Partsdata**. I en framtida version inkluderas postnummer och elektroniska adresser.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar krävs:

+ [Azure-abonnemang](https://portal.azure.com/)
+ [Åtkomst till mallen](https://aka.ms/dual-write-gab-adf)
+ Du är en befintlig kund.

## <a name="prepare-for-the-upgrade"></a>Förbereda uppgraderinge

+ **Fullt synkroniserat**: Båda miljöerna är helt synkroniserade för **Konto (kund)**, **Kontakt** och **Leverantör**.
+ **Integreringsnycklar**: Registren **Konto (Kund)**, **Kontakt** och **Leverantör** i program för kundengagemang använder de integreringsnycklar som levererades färdiga. Om du anpassar integreringsnycklarna måste du anpassa mallen.
+ **Partsnummer**: Alla **Kontro (kund)-**, **Kontakt-** och **Leverantörs** poster som ska uppgraderas har ett **Parts** nummer. Poster utan ett **Parts** nummer ignoreras. Om du vill uppgradera dessa poster lägger du till ett **Parts** nummer i dem innan du startar uppgraderingsprocessen.
+ **Systemavbrott**: Under uppgraderingen måste du ta både Finance and Operations-miljön och miljön för kundengagemang offline.
+ **Ögonblicksbild**: Ta ögonblicksbilder av både Finance and Operations-appen och appen för kundengagemang. Använd ögonblicksbilderna om du vill återställa föregående status vid behov.

## <a name="deployment"></a>Distribution

1. Hämta mallen från [Implementeringstillgångar för Dynamics-365-FastTrack](https://aka.ms/dual-write-gab-adf)

2. Logga in på [Microsoft Azure](https://portal.azure.com/).

3. Skapa en [resursgrupp](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Skapa ett [lagringskonto](/azure/storage/common/storage-account-create?tabs=azure-portal) i resursgruppen som du skapade.

5. Skapa en [datafabrik](/azure/data-factory/quickstart-create-data-factory-portal) i resursgruppen som du skapade ovan.

6. Öppna datafabriken och välj panelen **Skapa och övervaka**.

7. På fliken **Hantera** väljer du **ARM-mall**.

8. Välj **Importera ARM-mall** för att importera mallen **Part**.

9. Importera mallen till datafabriken. Ange följande värden för **Projektinformation** och **Instansinformation**.

    Fält | Värde
    ---|---
    Abonnemang | Azure-abonnemang
    Resursgrupp | Ange samma resurs under vilken lagringskontot skapas.
    Region | Ange region.
    Fabriksnamn | Ange fabriksnamn.
    Huvudservicenyckel för kopplad FO-service | Ange nyckeln för ansökan
    Anslutningssträng för Azure Blob Storage | Anslutningssträng för Azure Blob-lagring.
    Kopplat tjänstelösenord för Dynamics Crm | Lösenordet för det användarkonto du angett som användarnamn.
    FO Linked Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO Linked Service_properties_type Properties_tenant | Ange information om klientorganisation (domännamn eller ID för klientorganisation) under vilket programmet finns.
    FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO Linked Service_properties_type Properties_service Principal Id | Ange programmets klient-ID.
    Dynamics Crm Linked Service_properties_type Properties_username | Användarnamnet som ska kopplas till Dynamics.

    Mer information finns i [Flytta upp en Resource Manager-mall för respektive miljö manuellt](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Kopplade tjänsteegenskaper](/azure/data-factory/connector-dynamics-ax#linked-service-properties) samt [Kopiera data med hjälp av Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Efter distributionen kan du validera datauppsättningarna, dataflödet och länkad tjänst för datafabriken.

   ![Datauppsättningar, dataflöde och länkad tjänst](media/data-factory-validate.png)

11. Navigera till **Hantera**. Under **Anslutningar** väljer du **Kopplad tjänst**. Välj **DynamicsCrmLinkedService**. Ange följande värden i formuläret **Redigera kopplad tjänst (Dynamics CRM)**:

    Fält | Värde
    ---|---
    Namn | DynamicsCrmLinkedService
    beskrivning | Kopplade tjänster för anslutning med CRM-instans för hämtning av entitetsdata
    Anslut via integreringskörning | AutoResolvelntegrationRuntime
    Distributionstyp | Online
    Service-Uri | `https://<organization-name>.crm[x].dynamics.com`
    Autentiseringstyp | Office365
    Användarnamn |
    Lösenord eller Azure-nyckelvalv | Lösenord
    Lösenord |

## <a name="run-the-template"></a>Kör mallen

1. Stoppa följande dubbelskrivning för **Konto**, **Kontakt** och **Leverantör** med hjälp av Finance and Operations-programmet.

    + Kunder V3 (konton)
    + Kunder V3 (kontakter)
    + CDS-kontakter V2 (kontakter)
    + CDS-kontakter V2 (kontakter)
    + Leverantör V2 (msdyn_vendor)

2. Kontrollera att kartorna har tagits bort från `msdy_dualwriteruntimeconfig`-registret i Dataverse.

3. Installera [lösningar för dubbel skrivningspart och global adressbok](https://aka.ms/dual-write-gab) från AppSource.

4. Om följande register innehåller data i Finance and Operations-programmet kör du sedan **Initial synkronisering** för dem.

    + Tilltal
    + Typer av personliga egenskaper
    + Avslutningsfras
    + Kontaktpersonens titlar
    + Roller för beslutsfattare
    + Lojalitetsnivåer

5. Inaktivera följande instickssteg i programmet för kundengagemang.

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

    ![Utlösarkörning](media/data-factory-trigger.png)

    > [!NOTE]
    > Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen.

8. Importera de nya **Part**-posterna i Finance and Operations-programmet.

    + Hämta filen `FONewParty.csv` från Azure blob-lagring. Sökvägen är `partybootstrapping/output/FONewParty.csv`.
    + Konvertera filen `FONewParty.csv` till en Excel-fil och importera Excel-filen till Finance and Operations-programmet.  Om CSV-importen fungerar kan du importera CSV-filen direkt. Importen kan ta ett par timmar att köra, beroende på datavolymen. Mer information finns i [Översikt över dataimport- och exportjobb](../data-import-export-job.md).

    ![Importera poster för Datavers-parten](media/data-factory-import-party.png)

9. Aktivera följande instickssteg i programmet för kundengagemang:

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

10. Aktivera följande arbetsflöden i kundkopplingsprogrammen om du inaktiverat dem i föregående steg:

    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer i tabellen Konton
    + Skapa leverantörer av typen "person" i registret Kontakter
    + Skapa leverantörer av typen person i tabellen Leverantörer
    + Uppdatera leverantörer i tabellen Konton
    + Uppdatera leverantörer i tabellen Leverantörer
    + Uppdatera leverantörer av typen person i tabellen Kontakter
    + Uppdatera leverantörer av typen person i tabellen Leverantörer

11. Kör de **part** relaterade kartorna enligt instruktionerna i [Part och global adressbok](party-gab.md).

## <a name="troubleshooting"></a>Felsökning

1. Om processen misslyckas kör du datafabriken igen, med början från den misslyckade aktiviteten.
2. Vissa filer genereras av den datafabrik som du kan använda för datavalidering.
3. Datafabriken körs baserat på CSV-filer som är kommaavgränsade. Om det finns ett fältvärde med ett kommatecken kan detta komma att störa resultaten. Du måste ta bort kommatecknen.
4. På fliken **Övervakning** finns information om alla steg och data som bearbetas. Välj ett specifikt steg för att felsöka det.

    ![Fliken Övervakning](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Läs mer om mallen

Det finns kommentarer för mallen i filen [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).