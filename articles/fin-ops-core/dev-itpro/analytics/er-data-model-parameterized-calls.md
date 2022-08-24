---
title: Stödparameteriserade anrop rörande ER-datamodeller
description: I denna artikel beskrivs hur du implementerar parameteriserade anrop i datamodeller för elektronisk rapportering (ER).
author: kfend
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
ms.openlocfilehash: 5be189c19d963991ec012de189bbf7b721b88fef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276001"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Stödparameteriserade anrop rörande ER-datamodeller

[!include [banner](../includes/banner.md)]

Om du vill generera affärsdokument konfigurerar du en [lösning med elektronisk rapportering (ER)](general-electronic-reporting.md) som innehåller följande ER-komponenter:

- **[Format](er-overview-components.md#format-component)** – Denna komponenten anger strukturen i ett affärsdokument.
- **Formatmappning** – Denna komponent styr hur ett affärsdokument fylls i vid körning.
- **[Modellmappning](er-overview-components.md#model-mapping-component)** – Denna komponent anger vad datan hämtar från programmet till en formatmappning.
- **[Datamodell](er-overview-components.md#data-model-component)** – Denna komponenten skickar information mellan enskilda komponenter.

När du kör ett ER-format körs varje formatelement, med början från rotformatelementet. När ett formatelement som körs innehåller en koppling till en [datakälla](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents) körs datakällan för att leverera förväntade data och använda denna för att fylla i formatelementet. När en datakälla av typen *Modell* anropas. anropas lämplig modellmappning för att hämta data ur programmet baserat på inställningarna för modellmappning.

Tidigare har dessa modellmappningsanrop inte kunnat parameteriseras för att göra dem beroende av logiken i formatet som körs. Endast det följande dataflödet stöddes.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Format&nbsp;element<br>
&nbsp;
</td>
<td>
<i>Bindning</i><br>
&gt;&nbsp;begäran&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;&lt;
</td>
<td><b>Format&nbsp;mappning</b><br>
Datakälla<br>
&nbsp;
</td>
<td>
<i>Datamodell</i><br>
&gt;&nbsp;begäran&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;&lt;
</td>
<td>
<b>Modellmappning</b><br>
Datakälla<br>
&nbsp;
</td>
<td>
<i>Bindning</i><br>
&gt;&nbsp;begäran&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;&lt;
</td>
<td>
<b>Register</b><br>
Registrera<br>
Fält
</td>
</tr>
</tbody>
</table>

I version 10.0.15 och senare kan du dock konfigurera datamodellfält som endast kan anropas när värdena för de konfigurerade parametrarna finns. När ett sådant fält är konfigurerat och anropas från en formatkomponent måste de nödvändiga parametrarna anges i en formatbindning som argument för anropet. I dessa fall kan värdena i argumenten anges baserade på formatspecifika värden. Därför kan du använda **dynamisk körningsparametrisering** för datamodellanrop för att stödja följande dataflöde.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Formatelement&nbsp;1<br>
<br>
Formatelement&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Bindning</i><br>
&gt;&nbsp;begäran&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;begäran&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Formatmappning</b><br>
Datakälla&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Datamodell</i><br>
&gt;&nbsp;fält1&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;fält2(värde2)&nbsp;&gt;</b><br>
&lt;&nbsp;värde&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Modellmappning</b><br>
Datakälla&nbsp;1<br>
<br>
Datakälla&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Bindning</i><br>
&gt;&nbsp;begäran&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;begäran&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;värde&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Register&nbsp;1</b><br>
Post&nbsp;1<br>
Fält&nbsp;1<br>
<b>Register&nbsp;2</b><br>
Post&nbsp;2<br>
Fält&nbsp;2
</td>
</tr>
</tbody>
</table>

Med hjälp av de nya funktionerna kan du parametrisera anropet till valfritt datamodellfält av typen [*Post*](er-formula-supported-data-types-composite.md#record) eller [*Postlista*](er-formula-supported-data-types-composite.md#record-list). Följande datatyper stöds för parametrarna i ett datamodellfält:

- [Booleskt](er-formula-supported-data-types-primitive.md#boolean)
- [Container](er-formula-supported-data-types-composite.md#container)
- [Datum](er-formula-supported-data-types-primitive.md#date)
- [DatumTid](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Heltal](er-formula-supported-data-types-primitive.md#integer)
- [Realtal](er-formula-supported-data-types-primitive.md#real)
- [Sträng](er-formula-supported-data-types-primitive.md#string)

Du kan ange repsektive parameter i ett datamodellfält för vilket argumentet kan anges som ett enskilt värde för den definierade datatypen och [*listan*](er-formula-supported-data-types-composite.md#record-list) med sådana värden.

> [!NOTE]
> Standardvärdet för parametern för ett datamodellfält stöds inte. Om du lägger till en parameter i ett fält i en datamodell, och versionen av den datamodellen redan har frisläppts och publicerats, måste du [basera om](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) alla motsvarande modellmappningar och -format till den nya versionen av den här modellen, detta eftersom den här datamodellen inte är bakåtkompatibel.

Du kan konfigurera parametriserade datamodellfält så att modellmappningsanropen blir formatspecifika. Detta arbetssätt kan hjälpa dig att minska antalet modellmappningar som måste konfigureras för många format för en enskild datamodell. Du kan också använda den här metoden om du vill förbättra körningsprestandan i dina format och minska den tid som krävs för att generera affärsdokument. Om du vill veta mer om den här funktionen fyller du i exemplet i den här artikeln.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Exempel: Använd parameteriserade anrop av ER-datamodeller

I följande steg förklaras hur en användare med rollen Systemadministratör eller Elektronisk rapporteringsutvecklare kan designa en ER-lösning som innehåller en datamodell, en modellmappning och en ER-formatkomponent som är konfigurerad att anropa en modellmappning från ett format genom att tillhandahålla ett argument för anropet vars värde har beräknats vid körning med hjälp av formeln för körningsformatet. 

Dessa steg kan slutföras i **DEMF**-företaget. Inga kodändringar krävs. 

I det här exemplet ska du skapa erforderliga ER-[konfigurationer](general-electronic-reporting.md#Configuration) för exempelföretaget **Litware, Inc.**. Se till att konfigurationsprovidern för exempelföretaget **Litware, Inc.** (`http://www.litware.com`) har listats för ER-ramverket samt att det har markerats som **Aktivt**. Om denna konfigurationsleverantör inte finns med i listan, eller om den inte är markerad som **Aktiv**, följer du stegen i [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Affärsscenario

Du har en ER-lösning som innehåller ett format som du kan köra för att skapa ett elektroniskt dokument för granskningsändamål. Formatet innehåller momstransaktioner som är relaterade till försäljningsorder och inköpsorder, och som har de uppgifter som krävs, till exempel transaktionsdatum och momsvärde. Strukturen i det här dokumentet har ändrats från och med det nya räkenskapsåret. Du måste nu skicka in ett utökat dokument som innehåller ytterligare uppgifter (namn) för alla parter (kunder och leverantörer) vars transaktioner visas i genererade rapporter. Du måste därför ändra ER-lösningen så att den genererar dokument som uppfyller detta nya krav.

### <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra dessa inställningar innan du börjar använda ER-ramverket för att designa en ny ER-lösning.

### <a name="design-a-domain-specific-data-model"></a>Ange urvalskriterier i dialogrutan för frågeformulär

Du måste skapa en ny ER-konfiguration som innehåller erforderlig datamodellkomponent. Denna datamodell kommer senare att användas som datakälla när du designar ett ER-format för att generera en granskningsrapport.

Följ anvisningarna nedan och importera önskad datamodell från en XML-fil som tillhandahålls av Microsoft.

1. Hämta filen [Sample audit model.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Sample audit model.version.1.xml**.
6. Välj **OK** för att importera konfigurationen.

    ![Importerad konfiguration av ER-datamodell på sidan Konfigurationer.](./media/er-data-model-parameterized-calls-imported-model.png)

Följande bild illustrerar den redigerbara versionen av den konfigurerade datamodellen på sidan **Datamodelldesigner**.

![Struktur för ER-datamodellen på sidan Datamodelldesigner.](./media/er-data-model-parameterized-calls-model1.png)

För närvarande är modellen utformad för att endast visa momstransaktioner som har de detaljer som krävs.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Designa en modellmappning för den konfigurerade datamodellen

Som användare i rollen som elektronisk rapporteringsutvecklare måste du skapa en ny ER-konfiguration som innehåller en modellmappningskomponent för datamodellen för exempelgranskning. Denna komponent implementerar den konfigurerade datamodellen för Microsoft Dynamics 365 Finance och är specifik för den appen. Du måste konfigurera komponenten för modellmappning för att ange vilka programobjekt som ska användas för att fylla i den konfigurerade datamodellen med programdata vid körning. För att slutföra den här uppgiften måste du förstå hur datastrukturen i affärsdomänen för moms implementeras i Ekonomi.

Följ dessa steg för att importera önskad modellmappning från en XML-fil som tillhandahålls av Microsoft.

1. Hämta filen [Sample audit model mapping.version.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Sample audit model mapping.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

    ![Importerad mappningskonfiguration av ER-modell på sidan Konfigurationer.](./media/er-data-model-parameterized-calls-imported-mapping.png)

Bilden nedan visar den redigera versionen av den konfigurerade modellmappningen på sidan **Modellmappningsdesigner**.

![Struktur för ER-modellmappningen på sidan Modellmappningsdesigner.](./media/er-data-model-parameterized-calls-mapping1.png)

För närvarande är modellmappningen utformad för att visa momstransaktioner som har de detaljer som krävs. Den hämtar denna information från programregistret `TaxTrans` hjälp av de konfigurerade ER-datakällorna `TaxTrans` och `TaxTransFiltered`.

### <a name="design-a-new-format"></a>Designa ett nytt

Som användare i rollen funktionell konsult för elektronisk rapportering måste du skapa en ny ER-konfiguration som innehåller komponenten format. Du måste konfigurera formatkomponenten för att fylla i genererade rapporter med momstransaktioner som innehåller all information som behövs.

Följ anvisningarna nedan för att importera önskat format från en XML-fil som tillhandahålls av Microsoft.

1. Hämta filen [Sample audit format.version.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Sample audit format.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

    ![Importerad ER-formatkonfiguration på sidan Konfigurationer.](./media/er-data-model-parameterized-calls-imported-format.png)

Bilden nedan visar den redigerbara versionen av det konfigurerade formatet på sidan **Formatdesigner**.

![Struktur för ER-formatet på sidan Formatdesigner.](./media/er-data-model-parameterized-calls-format1.png)

ER-formatet konfigureras till att generera en rapport som en textfil med kommaavgränsade värden (CSV).

### <a name="run-the-imported-format"></a>Kör det importerade formatet

1. På sidan **Konfigurationer** väljer du konfigurationen **Exempelgranskningsformat** och väljer sedan **Kör** i åtgärdsfönstret.
2. I dialogrutan **Parametrar för elektronisk rapport**, på fliken **Poster att inkludera**, väljer du **Filter**.
3. Ange villkoren för att välja momstransaktionerna för verifikationerna **PIV-110000004** och **INV-10000001**.
4. Välj **OK**.
5. Välj **OK**.
6. Granska det genererade dokumentet som innehåller momstransaktioner för de valda verifikationerna.

    ![Förhandsgranskning av det genererade dokumentet med momstransaktioner.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Justera den importerade ER-lösningen

Enligt det nya kravet måste det dokument du måste skicka innehålla namnen på kunder och leverantörer vars transaktioner ingår. Du måste därför ändra den importerade ER-lösningen så att denna genererar ett dokument som uppfyller detta nya krav.

Bestäm hur du vill implementera erforderliga ändringar av de importerade ER-komponenterna.

Den bästa metoden är att implementera följande ändringar:

- Lägg till det nya datamodellfältet `Transaction.Party.Name` av typen *Sträng* i din datamodell.
- Konfigurera bindningen för det nya datamodellfältet i modellmappningen genom att använda tillgängliga registerrelationer för att komma åt den relevanta posten i `DirPartyTable`-programregistret och hämta värdet i fältet `Name` från detta.

Även om denna metod fungerar kan den orsaka prestandaproblem i SQL-databasen, detta eftersom `TaxTrans` är transaktionsregistret och därför kan innehålla ett stort antal poster. I detta fall måste antalet anrop till `DirPartyTable` vara lika med antalet poster i `TaxTrans`-registret som kan medföra prestandaproblem.

Du kan också implementera följande ändringar:

- Lägg till den nya roten `Party` och det nya fältet `Party.Name` i din datamodell.
- I modellmappningen lägger du till en ny datakälla som sammanfogar alla poster i register som används i registerrelationer för att komma åt den relevanta posten i `DirPartyTable`-programregistret, med start från `TaxTrans`-registret.

Även om denna metod fungerar kan den leda till problem med minnesförbrukning. Även om en ny [JOIN](er-join-data-sources.md)-datakälla körs som en enda SQL-begäran till programdatabasen i syfte att förhindra problem med databasprestanda måste resultatet hämtas till programserverns minne. Eftersom antalet poster och antalet fält i dessa poster kommer att bli rätt stort kan denna metod leda till mycket omfattande minnesförbrukning. Till och med ett undantag på grund av otillräckligt minne vid körning kan inträffa.

Du kan implementera ändringarna när ett körningsformat samlar in (i minnet) de unika identifieringskoderna för kunder och leverantörer för samtliga momstransaktioner som visas i en genererad rapport. Eftersom bara unika koder ska förvaras är den slutliga uppsättningen koder inte stor nog att påverka minnesförbrukningen. Koduppsättningen överförs sedan till modellmappningen som argument för ett annat anrop för datakällan av typen *Modell*. Baserat på detta anrop kör modellmappningen en ny ER-datakälla som gör en enskild SQL-begäran till programdatabasen för att, fårn registret `DirPartyTable`, endast hämta poster för de parter vars koder visas i den angivna koduppsättningen.

### <a name="adjust-the-imported-data-model"></a>Justera den importerade datamodellen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i konfigurationsträdet i vänster panel väljer du **Exempelgranskningsmodell**.
3. På snabbfliken **Versioner** väljer du version **2** med statusen **Utkast**.
4. Klicka på snabbfliken **konfigurationskomponenter**.
5. Välj **Designer** om du vill öppna datamodellen för redigering.
6. På sidan **Datamodell** kontrollerar du att fältet `Root` har markerats innan du väljer **Ny**.
7. Gör följande i listrutan:

    1. I fältgruppen **Ny nod som** väljer du alternativet **Underordnat objekt till aktiv nod**.
    2. I fältet **Namn** anger du **Part**.
    3. Välj **Postlista** i fältet **Artikeltyp**.
    4. Klicka på **Lägg till** om du vill sluta lägga till det nya fältet.

8. Se till att fältet `Root.Party` har valts innan du på fliken **Nod** väljer **Parametrar**.
9. I dialogrutan **Parametrar** utför du följande steg:

    1. På fliken **Parametrar** väljer du **Ny**.
    2. I fältet **Namn** anger du **PartyRefRecId**.
    3. I fältet **Typ** väljer du **Int64**.
    4. Markera kryssrutan **Lista**.
    5. Välj **OK** om du vill avsluta inmatningen av parametrarna.

    > [!NOTE]
    > Du konfigurerade precis datamodellfältet `Root.Party` som ett fält som anropas när ett värde anges i parametern **PartyRefRecId**. Detta värde måste finnas i listan över poster som innehåller ett `Value`-fält av datatypen *Int64*.

    ![Dialogrutan Parametrar.](./media/er-data-model-parameterized-calls-model2a.png)

10. Kontrollera att fältet `Root.Party` fortfarande är markerat och välj sedan **Ny**.
11. Gör följande i listrutan:

    1. I fältgruppen **Ny nod som** väljer du alternativet **Underordnat objekt till aktiv nod**.
    2. I fältet **Namn** anger du **Namn**.
    3. Välj **Sträng** i fältet **Artikeltyp**.
    4. Klicka på **Lägg till** om du vill sluta lägga till det nya fältet.

12. Välj **Spara** och stäng sedan sidan **Datamodell**.

    ![Struktur för justerad ER-datamodell på sidan Datamodelldesigner.](./media/er-data-model-parameterized-calls-model2b.png)

13. På snabbfliken **Versioner** väljer du, för version **2**, **Ändra status** \> **Slutför**. Välj sedan **OK**.

    > [!NOTE]
    > Dina datamodelländringar lagras i den andra revisionen av datamodellkomponenten **Exempelgranskningsmodell** som finns i den andra versionen av konfigurationen **Exempelgranskningsmodell**.

![Uppdaterade konfiguration för ER-datamodell på sidan Konfigurationer.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Justera den importerade modellmappningen

1. På sidan **Konfigurationer**, i konfigurationsträdet i vänstra fönster, visar du **Exempelgranskningsmodell**.
2. Välj **Mappning för exempelgranskningsmodell** innan du på snabbfliken **Versioner** väljer den andra mappningsversionen som baseras på den första datamodellverionen (version **1.2**) och som har statusen **Utkast**.
3. Välj **Basera om**.
4. I fältet **Målversion** lämnar du version **2** av basmodellen **Exempelgranskningsmodell** som den är.
5. Välj **OK** att basera om och anpassa modellmappningen efter de senaste datamodelländringarna.

    Notera att versionsnumret för din redigerbara modellmappning har ändrats från **1.2** till **2.2** i syfte att indikera att den andra modellversionen för närvarande används som bas.

6. Välj **Designer**.
7. På sidan **Modell för mappning av datakälla** väljer du **Designer** för aktuell modellmappning.
8. Följ dessa steg om du vill lägga till en ny datakälla för åtkomst till `DirPartyTable`-programregistret:

    1. I fönstret **Datakälltyp** väljer du **Dynamics 365 for Operations \> Registerposter**.
    2. I fönstret **Datakällor** välj **Lägg till rot**.
    3. I fältet **Namn** anger du **PartyTable**.
    4. I fältet **Register** anger du **DirPartyTable**.
    5. Klicka på **OK** om du vill sluta lägga till den nya datakällan.

9. Följ dessa steg om du vill lägga till en ny datakälla för att begära `DirPartyTable`-poster, baserat på den tillhandahållna listan med postidentifieringskoder:

    1. I fönstret **Datakälltyp** väljer du **Allmänt \> Tom behållare**.
    2. I fönstret **Datakällor** välj **Lägg till rot**.
    3. I fältet **Namn** anger du **Data**.
    4. Klicka på **OK** om du vill sluta lägga till den nya datakällan.
    5. I fönstret **Datakällor** väljer datakällan **Data**.
    6. I fönstret **Datakälltyp** väljer du **Funktioner \> Beräknade fält**.
    7. I fönstret **Datakällor** väljer du **Lägg till**.
    8. I fältet **Namn** anger du **DirParty**.
    9. Välj **Redigera recept**.
    10. På sidan **Formeldesigner** väljer du **Parametrar**.
    11. I dialogrutan **Parametrar** utför du följande steg:

        1. På fliken **Parametrar** väljer du **Ny**.
        2. I fältet **Namn** anger du **DirPartyId**.
        3. I fältet **Typ** väljer du **Int64**.
        4. Markera kryssrutan **Lista**.
        5. Välj **OK**.

        > [!NOTE]
        > Du konfigurerade just detta beräknade fält så att det vid körning accepterar argumenten för en enskild parameter som konfigurerats som en postlista med ett enda `Value`-fält av typen *Int64*.

    12. I fältet **formel** anger du följande uttryck:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Du konfigurerade just det beräknade fältet `DirParty` till att endast hämta `DirPartyTable`-poster där postidentifieringskoderna finns med i den `DirPartyId`-lista som tillhandahålls som ett argument när `DirParty`-fältet anropas.

        ![Formel för att hämta partsnamn från programregistret på sidan Formeldesigner.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Stäng sidan **Spara** och **Formeldesigner**.
    14. Välj **Spara** och sedan **OK** för att sluta lägga till den nya datakällan.

10. Följ dessa steg om du vill binda den nya datakällan till det nya datamodellfältet så att datamodellen används för att exponera partnamn:

    1. I fönstret **Datamodell** väljer du datamodellfältet `Root.Party`.
    2. I fönstret **Datamodell** välj **Redigera**.
    3. På sidan **Formeldesigner**, i fältet **Formel**, anger du uttrycket `Data.DirParty(PartyRefRecId)`.
    4. Stäng sidan **Spara** och **Formeldesigner**.

        > [!NOTE]
        > Du konfigurerade precis bindningen för att anropa den konfigurerade `Data.DirParty`-datakällan och tillhandahålla listan över postidentifieringskoder som anges i formatet när datamodellfältet `Root.Party` anropas.

    5. I fönstret **Datamodell** väljer du datamodellfältet `Root.Party.Name`.
    6. I fönstret **Datamodell** välj **Redigera**.
    7. På sidan **Formeldesigner**, i fönstret **Datakälla**, visar du **Data \> DirParty** och väljer sedan **Namn**.
    8. Välj **Lägg till datakälla**.
    9. Stäng sidan **Spara** och **Formeldesigner**.

    ![Struktur för justerad ER-modellmappning på sidan Modellmappningsdesigner.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Välj **Spara** och stäng sidan **Modellmappningsdesigner**.
12. Stäng sidan **modell till mappning av datakälla**.
13. På snabbfliken **Versioner** väljer du för version **2.2** **Ändra status \> Slutför**. Välj sedan **OK**.

### <a name="adjust-the-imported-format"></a>Justera det importerade formatet

1. På sidan **Konfigurationer** väljer du **Exempelgranskningsformat**.
2. På snabbfliken **Versioner** väljer du version **1.2** med statusen **Utkast**.
3. Välj **Basera om**.
4. I fältet **Målversion** lämnar du version **2** av basmodellen **Exempelgranskningsmodell** som den är.
5. Välj **OK** för att basera om och anpassa ditt format efter de senaste datamodelländringarna.
6. Välj **Designer**.
7. På sidan **Formatdesigner**, i formatstrukturen i det vänstra fönstret, väljer du **Visa/Dölj**.
8. Följ dessa steg om du vill lägga till ett nytt formatelement för att samla in postidentifieringskoder för parter vars transaktioner visas i genererade rapporter.

    1. I formatstrukturträdet väljer du sekvenselementet **Report.Row.Trans**.
    2. Markera **Lägg till**.
    3. I dialogrutan **Lägg till** väljer du **Datakälla \> Artikel**.
    4. I dialogrutan **Komponentegenskaper**, i fältet **Namn**, anger du **Id**.
    5. I fältet **Datatyp** väljer du **Int64**.
    6. Välj **OK**.

    > [!NOTE]
    > Ett element av typen **Datakälla \> Artikel** kan endast användas för interna beräkningar och datatransformering i körningsformatet. Genom att lägga till detta formatelement ändras alltså inte innehållet i ett genererat dokument.

9. Följ dessa steg om du vill lägga till nya formatelement för att ange partnamn i genererade rapporter:

    1. Välj sekvenselementet **Report.Row**.
    2. Markera **Lägg till**.
    3. I dialogrutan **Lägg till** väljer du **Text \> Sekvens**.
    4. I dialogrutan **Komponentegenskaper**, i fältet **Namn**, anger du **Part**.
    5. Välj **OK**.
    6. Välj sekvenselementet **Report.Row.Party**.
    7. Markera **Lägg till**.
    8. I dialogrutan **Lägg till** väljer du **Text \> Sträng**.
    9. I dialogrutan **Komponentegenskaper**, i fältet **Namn**, anger du **Namn**.
    10. Välj **OK**.

10. Följ dessa steg om du vill lägga till en ny datakälla för att samla in postidentifieringskoder för parter vars transaktioner visas i genererade rapporter:

    1. På fliken **Mappning** väljer du **Lägg till rot**.
    2. I dialogrutan **Lägg till datakälla** väljer du **Funktioner \> Datainsamling**.
    3. I dialogrutan **'Datakällparametrar för datainsamling**, i fältet **Namn**, anger du **PartyIds**.
    4. I fältet **Artikeltyp** väljer du **Int64**.
    5. Välj **OK**.

11. Följ dessa steg om du vill lägga till en ny bindning för att samla in postidentifieringskoder för parter vars transaktioner visas i genererade rapporter:

    1. I formatstrukturträdet väljer du datartikelelementet **Report.Row.Trans.Id**.
    2. Välj **Redigera recept**.
    3. På sidan **Formeldesigner** anger du uttrycket `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Stäng sidan **Spara** och **Formeldesigner**.

12. Följ dessa steg om du vill lägga till nya bindningar för att ange partnamn i genererade rapporter:

    1. I formatstrukturträdet väljer du sekvenselementet **Report.Party**.
    2. Välj **Redigera recept**.
    3. På sidan **Formeldesigner** anger du uttrycket `model.Party(PartyIds.Result)`.
    4. Stäng sidan **Spara** och **Formeldesigner**.
    5. I formatstrukturträdet väljer du sekvenselementet **Report.Party.Name**.
    6. På fliken **Mappning** väljer du datamodellfältet `model.Party.Name`.
    7. Välj **bind**.

    ![Struktur för justerat ER-format på sidan Formatdesigner.](./media/er-data-model-parameterized-calls-format2.png)

13. Välj **Spara** och stäng sidan **Formatdesigner**.
14. Stäng sidan **modell till mappning av datakälla**.
15. På snabbfliken **Versioner** väljer du, för version **2.2**, **Ändra status** \> **Slutför**. Välj sedan **OK**.

### <a name="run-the-adjusted-format"></a>Kör det justerade formatet

1. På sidan **Konfigurationer** väljer du konfigurationen **Exempelgranskningsformat** och väljer sedan **Kör** i åtgärdsfönstret.
2. I dialogrutan **Parametrar för elektronisk rapport**, på fliken **Poster att inkludera**, väljer du **Filter**.
3. Ange villkoren för att välja momstransaktioner för verifikationerna **PIV-110000004** och **INV-10000001**.
4. Välj **OK**.
5. Välj **OK**.
6. Granska det genererade dokumentet som innehåller momstransaktioner för de valda verifikationerna och namnen på motsvarande kund och leverantör.

    ![Förhandsgranskning av det genererade dokumentet med momstransaktioner och partnamn.](./media/er-data-model-parameterized-calls-output2.png)

7. Gå till **Leverantörsreskontra** \> **Leverantörer** \> **Alla leverantörer** och granska information om vald **PIV-110000004**-verifikation, inklusive leverantörsnamnet.

    ![Granska inköpsverifikationsinformationen på sidorna Alla leverantörer och Fakturajourn.](./media/er-data-model-parameterized-calls-review1.gif)

8. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder** och granska informationen om vald **INV-10000001**-verifikation, inklusive kundens namn.

    ![Granska försäljningsverifikationsinformationen på sidorna Alla kunder och Bokförd moms.](./media/er-data-model-parameterized-calls-review2.gif)

Mer information om denna körning av ER-lösningen finns i den ER-inbyggda parsern för [prestandaspårning](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Stödparameteranrop till ER-datakällor för typen beräknat fält](er-calculated-field-type.md)
- [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md)
- [Använd datakällor för DATAINSAMLING i elektroniska rapporteringsformat](er-data-collection-data-sources.md)
- [ER-funktionen ValueInLarge](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
