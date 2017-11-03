---
title: "Jobb för import och export av data"
description: "Använda arbetsytan Datahantering för att skapa och hantera dataimport- och dataexportjobb."
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c788b018f621144755cc0b4ee4b55cb633cd81be
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="data-import-and-export-jobs"></a>Jobb för import och export av data

[!include[banner](../includes/banner.md)]

Om du vill skapa och hantera dataimport- och dataexportjobb i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, använd då arbetsytan **Datahantering**. Som standard skapar processen för dataimport och -export ett mellanlagringsregister för varje enhet i måldatabasen. Med tillfälliga register kan du kontrollera, rensa eller konvertera data innan du flyttar den.

## <a name="data-importexport-process"></a>Process för dataimport och -export
Här följer stegen för att importera eller exportera data.

1. Skapa ett import- eller exportjobb där du vill göra följande:

    - Definiera projektkategorin.
    - Leta upp de enheter som du vill importera eller exportera.
    - Ange dataformat för jobbet.
    - Ordna enheterna så att de behandlas i logiska grupper och i den serie som passar.
    - Bestäm om du vill använda tillfälliga register.

2. Validera att källdata och måldata mappas korrekt.
3. Kontrollera säkerheten för import- eller exportjobbet.
4. Kör import- eller exportjobbet.
5. Validera att jobbet har körts som förväntat genom att granska jobbhistoriken.
6. Rensa tillfälliga register.

Övriga avsnitt i det här avsnittet innehåller mer information om varje steg i processen.

## <a name="create-an-import-or-export-job"></a>Skapa ett import- eller exportjobb
Ett dataimport- eller -exportjobb kan köras en gång eller flera gånger.

### <a name="define-the-project-category"></a>Definiera projektkategorin
Vi rekommenderar att du lägger tid på att välja en lämplig projektkategori för ditt import- eller exportjobb. Projektkategorier hjälper dig att hantera relaterade jobb.

### <a name="identify-the-entities-to-import-or-export"></a>Leta upp de enheter som du vill importera eller exportera
Du kan lägga till specifika enheter i import- eller exportjobb eller välja den mall som ska användas. Mallar fyller ett projekt med en lista över enheter. Alternativet **Tillämpa mall** blir tillgängligt när du namnger ett jobb och spara det.

### <a name="set-the-data-format-for-the-job"></a>Ange dataformat för jobbet
När du väljer en enhet markerar du format för de data som ska exporteras eller importeras. Du definierar format via panelen **Inställningar för datakälla**. Många organisationer utgår från de format som ingår som standard i demonstrationsdatauppsättningen. Här följer en lista över några av dessa format:

- AX (för data som måste importeras eller exporteras i samma format som används för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition)
- Kolonseparerade
- CSV
- Excel
- Paket

### <a name="sequence-the-entities"></a>Ordna enheterna
Enheter kan ordnas i en datamall eller i import- och exportjobb. När du kör ett jobb som innehåller mer än en datatabell måste du kontrollera att datatabellerna har ordnats korrekt. Du ordnar entiteter i första hand så att du kan lösa eventuella funktionella samband mellan olika enheter. Om enheterna inte har några funktionella samband kan de schemaläggas parallell import eller export.

#### <a name="execution-units-levels-and-sequences"></a>Körningsenheter, -nivåer och -sekvenser
Körningsenheten, nivån i körningsenheten samt en enhets ordningsföljd hjälper till att styra i vilken serie som data exportera eller importeras.

- Enheter i olika körningsenheter behandlas parallellt.
- Om enheterna har samma nivå bearbetas de parallellt i respektive körningsnivå.
- På respektive nivå bearbetas enheterna enligt sina serienummer för just den nivån.
- När en nivå har bearbetats, bearbetas nästa nivå.

#### <a name="resequencing"></a>Omsekvensering
Du kanske vill omsekvensera dina enheterna i följande situationer:

- Om endast ett datajobb används för alla dina ändringar, kan du använda alternativen för omsekvensering för att optimera körningstiden för hela jobbet. I så fall kan du använda körningsenheten för att representera modulen, nivån för att representera modulens funktionsområde, samt sekvensen för att representera enheten. Med den här metoden kan du arbeta mellan olika moduler parallellt, men du kan ändå fortsätta att arbeta i följd i en modul. För att garantera att parallella operationer lyckas, måste du beakta alla beroenden.
- Du kan använda ordningsföljd för att enheternas nivå och serie i syfte att få en optimal körning om flera datajobb används (t.ex. ett jobb för varje modul).
- Om det inte finns några beroenden alls kan du ordna enheterna i olika körningsenheter i syfte att få en maximal optimering.

Menyn **Omsekvensering** finns att tillgå när du väljer flera enheter. Du kan omsekvensera baserat på alternativen för körningsenhet, nivå samt serie. Du kan ange ett ökningssteg i syfte att omsekvensera de enheter som har valts. Den enhet, den nivå eller det löpnummer som väljs för respektive entitet uppdateras med angivna steg.

#### <a name="sorting"></a>Sortering
Använd alternativet **Sortera** för att visa enhetslistan i ordningsföljd.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Bekräfta att källdata och måldata mappas korrekt
Mappning är en funktion som gäller både import- och exportjobb.

- Mappning beskriver vilka kolumner i källfilen som blir kolumner i det tillfälliga registret i samband med import. Därför kan systemet avgöra vilka kolumndata i källfilen som måste kopieras till vilken kolumn i det tillfälliga registret.
- Mappning beskriver vilka kolumner i det tillfälliga registret (dvs. källan) som kolumner i målfilen i samband med exportjobb.

Om kolumnnamnen i det tillfälliga registret och i filen stämmer överens, genererar systemet mappningen automatiskt baserat på namnen. Om namnen emellertid skiljer sig åt, mappas kolumnerna inte automatiskt. I så fall måste du slutföra mappningen genom att välja alternativet **Visa karta** alternativ för enheten i datajobbet.

Det finns två vyer för mappning: **Mappningsvisualisering**, som är standard, och **Mappningsdetaljer**. En röd asterisk (\*) markerar alla obligatoriska fält i enheten. Dessa fält måste mappas innan du kan arbeta med entiteten. Du kan ta bort mappningen av andra fält efter behov när du arbetar med enheten. Markera fältet som du vill ta bort mappningen för i kolumnen **Enhet** eller i kolumnen **Källa**, och välj sedan **Ta bort val**. Välj **Spara** om du vill spara ändringarna, och stäng sedan sidan om du vill återgå till projektet. Du kan använda samma process för att redigera fältmappning från källa till mellanlagring när du har importerat.

Du kan skapa en mappning på sidan genom att markera **Generera källmappning**. En genererad mappning fungerar som en automatisk mappning. Därför måste du mappa de omappade fälten manuellt.

![Datamappning](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Kontrollera säkerheten för import- eller exportjobbet
Åtkomsten till arbetsytan **Datahantering** kan begränsas så att icke-administratörer endast kan få åtkomst till specifika datajobb. Åtkomsten till data-jobbet innebär fullständig åtkomst till jobbets körningshistorik samt till mellanlagringsregistren. Därför måste du se till att en lämplig åtkomstkontroll finns på plats när du skapar ett datajobb.

### <a name="secure-a-job-by-roles-and-users"></a>Säkra ett jobb genom roller och användare
Använd menyn **Tillämpliga roller** om du vill begränsa jobbet till en eller flera säkerhetsroller. Endast användare med dessa roller får tillgång till jobbet.

Du kan även begränsa ett jobb till specifika användare. När du säkrar ett jobb med användare i stället för roller, ökar kontrollen om flera användare tilldelas en roll.

### <a name="secure-a-job-by-legal-entity"></a>Skydda ett jobb genom en juridisk person
Datajobb har en global karaktär. Om ett datajobb har skapats och använts i en juridisk person blir jobbet därför synlig för andra juridiska personer i systemet. Detta standardbeteende kan vara att föredras i vissa tillämpningsfall. En organisation som importerar fakturor genom datatabeller kan exempelvis innehålla ett centraliserat fakturabearbetningsteam som ansvarar för att hantera fakturafel för alla avdelningar inom organisationen. I det här scenariot är det bra om det centraliserade fakturabearbetningsteamet har åtkomst till fakturaimportjobb från alla juridiska personer. Därför uppfyller standardbeteendet kravet ur perspektivet för en juridisk person.

En organisation vill emellertid kanske ha fakturabearbetningsteam per juridisk person. I det här fallet bör ett team i en juridisk person bara ha åtkomst till fakturaimportjobbet i sin egen juridiska person. För att uppfylla detta krav kan du konfigurera åtkomstkontroll baserad på juridiska personer för datajobb via menyn **Tillämpbara juridiska personer** i datajobbet. När inställningarna har slutförts kan användarna bara se jobb som är tillgängliga i den juridiska personen som de för närvarande är inloggade på. Om de vill visa jobb från en annan juridisk person måste användarna växla till den juridiska personen.

Ett jobb kan skyddas med roller, användare och juridisk person samtidigt.

## <a name="run-the-import-or-export-job"></a>Kör import- eller exportjobbet.
Du kan köra ett jobb en gång genom att välja knappen **Importera** eller **Exportera** när du har definierat jobbet. Välj **Skapa återkommande datajobb** för att skapa ett återkommande jobb.

## <a name="validate-that-the-job-ran-as-expected"></a>Validera att jobbet har körts som förväntat
Jobbhistoriken blir tillgänglig för felsökning och undersökning för såväl import- som exportjobb. Historiska jobbkörningar ordnas efter tidsintervall.

![Intervall för jobbhistorik](./media/dixf-job-history.md.png)

Varje gång du kör jobbet erhåller du följande information:

- Information om körning
- Körningslogg

Körningsinformationen anger statusen för varje dataenhet som jobbet bearbetat. Därför kan du snabbt hitta följande information:

- Vilka enheter som har bearbetats
- Hur många poster som bearbetats för en enhet, och hur många som misslyckades
- Mellanlagringsposter för respektive enhet

Du kan hämta mellanlagringsdatan i en fil för exportjobb, eller också du kan hämta den i form av ett paket för import- och exportjobb.

Du kan också öppna körningsloggen från körningsinformationen.

## <a name="clean-up-the-staging-tables"></a>Rensa mellanlagringsregister
Du kan rensa mellanlagringstabeller genom att använda funktionen **Mellanlagringsrensning** i arbetsytan **Datahantering**. Du kan använda följande alternativ för att välja vilka poster som ska tas bort från vilka mellanlagringsregister:

- **Enhet** – Om bara en enhet är tillgänglig kommer samtliga poster i den enhetens mellanlagringstabell att raderas. Välj detta alternativ om du vill rensa alla data för enheten mellan alla dataprojekt och alla jobb.
- **Jobb-ID** – Om bara ett jobb-ID tillhandahålls, kommer alla poster för alla enheter i det valda jobbet att tas bort från tillhörande mellanlagringstabeller.
- **Dataprojekt** – Om bara ett dataprojekt har markerats kommer alla poster för alla entiteter och över alla jobb för det valda dataprojektet att tas bort.

Du kan också kombinera alternativen för att ytterligare begränsa den postuppsättning som raderas.

