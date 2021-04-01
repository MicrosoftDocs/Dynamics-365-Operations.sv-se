---
title: Aktiviteter för underhållsstopp
description: Detta ämne förklarar hur underhållsstopp används för att få en översikt över den kapacitet som krävs för att utföra underhållsjobb på specifika tillgångar under en angiven period.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenanceStopCopy, EntAssetMaintenanceStopObject, EntAssetObjectProductionStop, EntAssetProductionStopType, EntAssetMaintenanceStop
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6251422755cf39930d48221e9de82ef16b4d96a7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252928"
---
# <a name="maintenance-downtime-activities"></a>Aktiviteter för underhållsstopp

[!include [banner](../../includes/banner.md)]

Underhållsstopp används för att få en översikt över den kapacitet som krävs för att utföra underhållsjobb på specifika tillgångar under en angiven period. Du kan till exempel skapa en registrering av underhållsstopp för produktionsrad 10 i produktionshall 29-A på produktionsplatsen 02. Registreringen av underhållsstopp har en start- och sluttid som anger den period under vilken tillgångarna relaterade till underhållsstoppet inte är tillgängliga för produktion.

**Aktiviteter för underhållsstopp** är en översikt över underhållsschemarader och underhållsjobb för arbetsorder för relaterade tillgångar under en angiven period. Raderna för underhållsjobb för arbetsorder har alla ett förväntat startdatum inom underhållsstoppperioden. Du kan extrahera användbar information och göra justeringar i planerade underhållsjobb:

- Få en översikt över nödvändiga nedstängningsperioder för produktionsutrustning (tillgångar).  
- Få en översikt över planerat underhåll (timmar), grupperat efter kompetenser (ansvariga underhållsarbetargrupper eller underhållsarbetare), t.ex. kapacitetsbeläggning för elektriker, smeder eller andra underhållsarbetsgrupper som krävs för det planerade underhållsjobben.  
- Gör justeringar av underhållsschemarader eller underhållsjobb för arbetsorder som är relaterade till tillgångarna, t.ex. ändra förväntade start- och slut tider på en rad eller välj andra underhållsarbetare för att optimera arbetsflödet för underhållsarbetare och underhållsarbetargrupper.

När du har valt tillgångar för en underhållsstopptidsregistrering inkluderas alla öppna underhållsschemarader och underhållsjobb för arbetsorder relaterade till aktiva arbetsorder i registreringen av underhållsstopp.

## <a name="maintenance-downtime-activities"></a>Aktiviteter för underhållsstopp

Klicka på **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** för att öppna en lista med alla aktiviteter för underhållsstopp och visa informationen relaterad till aktiviteterna. Klicka på en länk i kolumnen **Aktiviteter för underhållsstopp** om du vill öppna informationsvyn. Bilden nedan visar ett exempel på listan **Aktiviteter för underhållsstopp**.

![Figur 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Skapa en aktivitet för underhållsstopp

1. Klicka på **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** eller **Aktiva aktiviteter för underhållsstopp**.

2. Klicka på **Ny**.

3. Infoga ett ID i fältet **Aktiviteter för underhållsstopp** och ett namn i fältet **Namn**.

4. Infoga perioden för underhållsstoppet i fälten **Startdatum/tid** och **Slutdatum/tid**.

5. På snabbfliken **Tillgångar för aktiviteter för underhållsstopp** > klicka på **Lägg till rad** om du vill lägga till tillgångar, en åt gången, för aktiviteten för underhållsstopp.

6. Klicka **Spara** när alla tillgångar har lagts till. Illustrationen nedan visar ett exempel på en aktivitet för underhållsstopp med relaterade tillgångar och underhållsjobb.

7. Underhållsjobben för arbetsordern och öppna underhållsschemarader som är relaterade till de valda tillgångarna visas på snabbflikarna **Resulterande underhållsjobb för arbetsorder** och **Underhållsschemarader**. På snabbfliken **Allmänt** > gruppen **Arbetsorder** > fältet **Prognostimmar för underhåll** och snabbfliken **allmänt** > gruppen **Underhållsschema** > fältet **Prognostimmar för underhåll**, visas det totala antalet timmar som har prognosticerats för underhållsjobb för arbetsorder och underhållsschemarader.

Bilden nedan visar ett exempel på detaljvyn **Aktiviteter för underhållsstopp**.

![Figur 2](media/20-preventive-maintenance.png)

>[!NOTE]
>Underhållsjobben för arbetsorder och underhållsschemarader relaterade till de valda till gångarna uppdateras automatiskt om nya arbetsorder eller underhållsschemarader skapas när du har skapat aktiviteten för underhållsstopp. Om du till exempel tidsplanerar underhållsplaner eller underhållsomgångar för de relaterade till gångarna två dagar efter att aktiviteten för underhållsstopp har skapats, läggs nya underhållsschemarader automatiskt till i aktiviteten för underhållsstopp.

8. I **Alla aktiviteter för underhållsstopp** > **Aktiviteter för underhållsstopp** > välj en aktivitet för underhållsstopp i listan och klicka på **Kapacitetsbeläggning** för att öppna dialogrutan **Beräkna kapacitetsbeläggning**. Använd den här dialogrutan när du vill få en översikt över kapacitetsbeläggningen, t.ex. datum, tillgångar, tillgångstyper och underhållsjobbtyper. Observera att de datum som visas i dialogrutan är de start- och slutdatum som valts i **Aktiviteter för underhållsstopp**. Beräkningen inkluderar tillgångar som rör aktiviteten för underhållsstopp.

9. I dialogen **Beräkna kapacitetsbeläggning** redigerar du start- och sluttider om det behövs, och väljer om du vill inkludera arbetsorder och underhållsscheman i beräkningen. Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningen ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångar för en funktionsplats, som väljs på aktiviteten för underhållsstopp, på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kapacitetsbeläggningsrader på alla de funktionsplatsnivåer som de är relaterade till.

10. Klicka på **OK** för att starta beräkningen. Det totala antalet timmar visas i översikten **Kapacitetsbeläggning**. På fliken **Kapacitetsbeläggning** > i åtgärdsfönstergrupperna **Gruppera efter...** klickar du på de relevanta knapparna för att få en mer detaljerad översikt över allokeringen av prognostiserade timmar. Bilden nedan visar resultaten av en beräkning av **Kapacitetsbeläggning**.

![Figur 3](media/21-preventive-maintenance.png)

11. När du har skaffat en översikt över kapacitetsbeläggningen, om du vill göra justeringar på underhållsjobben för arbetsorder eller underhållsschemarader, återgår du till informationsvyn **Aktiviteter för underhållsstopp** och väljer de rader du vill justera på snabbflikarna **Resulterande underhållsjobb för arbetsorder** och **Underhållsschemarader**.

12. Klicka på knappen **Justera** och uppdatera förväntade start- och slutdatum, servicenivå eller ansvariga underhållsarbetare för de valda underhållsjobben för arbetsorder eller underhållsschemaraderna.

13. Klicka på **OK** när du har gjort de nödvändiga justeringarna. 

>[!NOTE]
>Underhållsjobb för arbetsorder och underhållsschemarader som inte ingår i underhållsstopperioden efter att du har gjort justeringar tas automatiskt bort från **Aktiviteter för underhållsstopp**.

14. I **Alla aktiviteter för underhållsstopp** > **Aktiviteter för underhållsstopp** > välj en aktivitet för underhållsstopp i listan och klicka på **Artikelprognos** för att öppna dialogrutan **Beräkna artikelprognos**. Använd den här dialogrutan om du vill beräkna prognoser för artiklar (reservdelar och andra nödvändiga artiklar) och gruppera dem för att få en översikt, t.ex. efter datum, tillgång, tillgångstyp och underhållsjobbtyp. Observera att de datum som visas i dialogrutan är de start- och slutdatum som valts i **Aktiviteter för underhållsstopp**. Beräkningen omfattar reservdelar och artiklar som hör till de tillgångar som valts på aktiviteten för underhållsstopp.

15. I dialogen **Beräkna artikelprognos** redigerar du start- och sluttider om det behövs, och väljer om du vill inkludera arbetsorder och underhållsscheman i beräkningen. Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningen ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångar för en funktionsplats, som väljs på aktiviteten för underhållsstopp, på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kapacitetsbeläggningsrader på alla de funktionsplatsnivåer som de är relaterade till.

16. Klicka på **OK** för att starta beräkningen. Det totala antalet artikelprognoser visas i översikten **Artikelprognos**. På fliken **Artikelprognos** > åtgärdsfönstergrupperna **Gruppera efter...** klickar du på de relevanta knapparna för att få en mer detaljerad översikt över allokeringen av prognostiserade artiklar. Bilden nedan visar resultaten av en beräkning av **Artikelprognos**.

![Figur 4](media/22-preventive-maintenance.png)

- Du kan kopiera resurser från en aktivitet för underhållsstopp till en annan. I **Alla aktiviteter för underhållsstopp** väljer du knappen **Kopiera aktiviteter för underhållsstopp** och gör dina urval i fälten **Från aktiviteter för underhållsstopp** och **Till aktiviteter för underhållsstopp** och klickar på **OK**.
- I **Alla aktiviteter för underhållsstopp** klickar du på knappen **Underhållsschemarader** eller knappen **Aktiva arbetsorder** för att öppna relaterade listor och visa raderna som är relaterade till den valda aktiviteten för underhållsstopp.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]