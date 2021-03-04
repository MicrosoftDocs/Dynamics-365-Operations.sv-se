---
title: Boka intervjuer i Attract
description: Det här avsnittet innehåller information om intervjuplanering och återrapportering aktiviteter i Attract.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: shielas
ms.openlocfilehash: 33eba9796ca997fde4be9a46050207d313551bde
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462619"
---
# <a name="schedule-interviews-in-attract"></a>Boka intervjuer i Attract

[!include [banner](includes/banner.md)]

## <a name="scheduler-activity"></a>Schemaläggarens aktivitet

Aktiviteten schemaläggare är valfri och har två komponenter: kandidatens begäran om tillgänglighet och tidsplan. Komponenten kandidaten tillgänglighet kan du använda e-post för att begära den sökandes tillgänglighet. Komponenten schemaläggare ger möjligheten att tidsplanera intervjuer med kandidater och anställningsteamet.

Om du vill konfigurera schemaläggarens aktivitet att inkludera eller begränsa kandidater som ska tidsplaneras väljer du ett värde i fältet **Vem du tidsplanerar**. Tillgängliga alternativ är följande **alla kandidater**, **externa kandidater** och **interna kandidater**. Om du till exempel vill hoppa över interna kandidater i tidsplaneringens första runda kan du endast tilldela tidsplaneringsaktiviteten till externa kandidater genom att ange **Vem du tidsplanerar** till **externa kandidater**.

### <a name="candidate-availability-request"></a>Begär tillgänglighet för kandidat

Om du vill skicka e-post till kandidater för att begära deras tillgänglighet, ange alternativet **Begär tillgänglighet för kandidat**. Om du väljer alternativet, kommer det här steget inte att visas i anställningsprocessen för jobbet.

Klicka på skicka begäran tillgänglighet genom **Skicka begäran**, välj tillgängliga datum och en e-postmall och sedan skicka det till sökande.

[![Attract rekryterarens vy om du vill skicka begär tillgänglighet för kandidat](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

När sökande får ett e-postmeddelande svara på begäran kan de logga in på deras kandidatportal, välja datum som överensstämmer med deras tillgänglighet och klicka **skicka**.

### <a name="schedule"></a>Tidsplanera
Det finns flera konfigurationer för tidsplan för intervju använder och snabbt skapa och skicka intervjuslingan till intervjuare och kandidaten.

1. Klicka på **Skapa schema** och i rutan **Lägga till intervjuare**, listar intervjuare som ska ingå i intervjuarslingan.
[![Attract rekryterar vy om du vill börja planera en intervjuloop](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Om sökande har svarat på förfrågan intervju tillgängligheten, operativsystemet **Intervjudatum** installeras med deras val. Du kan välja ett annat datum om det behövs.
    
    Om du väljer flyttat **Gör detta till en panelintervju** grupp av intervjuare till vänster till en enkel panelloop när du vill skapa intervjun. Sedan behöver du definiera en viss ordning för intervjuerna.
    
    Intervjuschemat ska ordnas som bäst matchar deltagarnas tillgänglighet. Om det är en intern kandidat måste inkludera du deras tillgänglighet som en del av schemarekommendationen.
    
    Onlinemöten, markera fält **Lägg till Skype-möten** och varje händelseintervjun kommer att ha länk **Skype för företag** är tillgänglig.

2. Markera intervjun varaktigheten för varje intervju händelse och klicka på **OK** för att skapa schemat.

    Om **rekommendationer** är markerat kommer visas och intervjurutnätet kommer att vara förifylld. Du kommer att kunna se aktuell i kalendertillgängligheten för alla markerade intervjuare. Du kommer också kunna visa kalendern och om de är en intern kandidaten. För intervjuare och interna kandidater kan du visa deras upptagna tider, deras arbetstimmar, deras ej på kontorettid och även identifiera om de har markerat sina kalendrar när de arbetar på en annan plats för specifika tidsperioder. 

3. Om det finns inga förslag, i kolumnen **intervjuare** väljer du i ett klockslag, ange intervjuntitel, information och fylla i platsinformation efter behov. Kan du inkludera **Skype för företag** för intervjun.

4. Om du vill inkludera ytterligare intervjuare klickar du på rutnätskolumn **Lägg till intervju** att välja en eller flera intervjuare. Du kan använda ellipsalternativet (...) för att ta bort en intervju från slingan.
    
5. Om intervjuerna planeras i en annan tidszon, välj krävd stad/tidszonen från den nedrullningsbara listan i det övre högra hörnet. Intervjuarens tillgänglighetsrutnät uppdateras till den nya tidszonen. Tidszonen som valts visas nu också i vyn **intervjusammanfattning** som delas med intervjuare och kandidaten. 

6. Klicka på **skicka till intervjuare** för att skicka mötesinbjudan till inblandade intervjuare.

    När intervjubegäran skickats till intervjuare kan de svara direkt från e-postinbjudan som de får.

    >[!NOTE]
    > För alla 1:1-intervjuer skickas påminnelser till intervjuare per dygn om intervjuaren inte har svarat (accepterat eller avböjt) begäran om intervju.

    > Det finns inga automatiska påminnelser för begäran om intervju för alla panelintervjuer. För att utlösa en påminnelse manuellt, redigera intervjun och använd alternativet **uppdatera och skicka** för att skicka tillbaka begäran till intervjuare.

    Intervjuarens svar samlas in och visas i Attract. Om intervjuaren tackar nej till inbjudan, meddelas ändringar. För att se svaren i rutnätsvyn **schemaläggare**, klicka på bubbelikonen.

[![Attract rekryterarvy av en intervjuarens svar](./media/schedule-interviewer-response2.png)](./media/schedule-interviewer-response2.png)

7. När du är klar kan delas med sökande intervjuschemat klickar du på **skicka till kandidaten**. Du kan välja att visa eller dölja intervjuarens namn och platser med sökande.

8. Välj en e-postmall och skicka intervjusammanfattningen till kandidaten. Kandidaten kan visa informationen i deras e-post samt deras kandidatportal.
    
>[!NOTE] 
> Tillgängligheten för en kalender visas endast om kandidaten är intern. Endast en intern kandidat kan ska användas för att förbättra rekommendationer för intervjuschema. Kandidater (intern eller extern) kan för närvarande inte ta emot e-postinbjudningar, istället får kandidaterna endast en sammanfattning av intervjuerna.

Kandidater får e-post med sammanfattning av deras intervjuloop. E-postmeddelandena innehåller en .ics-fil som kan sparas på deras personliga kalendrar för enklare åtkomst och meddelanden om intervjun.

>[!TIP] 
> Om du skickar intervjuschemat igen till kandidater, får de en annan bifogad .ics-fil. Du bör uppdatera e-postmallar för kandidaternas intervjusammanfattning för att säkerställa att kandidaterna tar bort tidigare tillagda intervjuhändelser och inte ser dubbletter i deras kalender. 

## <a name="feedback-activity"></a>Feedbackaktivitet

Feedbackaktiviteten är valfri i en jobbmall. Denna aktivitet låter intervjudeltagare ange rekommendationer eller feedbackkommentarer för en sökande. 

För att inkludera eller begränsa kandidaterna för att ge feedback, välj ett värde i fältet **Vem som intervjuare bör ge feedback till**.  Tillgängliga alternativ är följande **alla kandidater**, **externa kandidater** och **interna kandidater**. Om du till exempel vill hoppa över interna kandidater i första rundan av tidsplanering anger du **Vem bör intervjuare ge feedback för** till **externa kandidater**.

Om du väljer fältet **Ärv feedbackdeltagare från anställningsteamet** kommer rekryterare, anställande chefer och intervjuare registreras automatiskt i feedback-aktiviteten. Organisationer kan låta intervjuare visa feedback för andra människor innan de skickar sin egen feedback. Organisationer kan även tillåta att intervjuare redigerar deras feedback när de har skickat sina kommentarer. Intervjuare påminns skicka feedback för nyligen gjorda intervjuer utifrån den förinställda konfigurationen som en del av jobbmallen. Anställande chefen eller en rekryterare för jobbet kan också välja att manuellt påminna intervjuaren om att skicka feedback.

## <a name="interview-activity"></a>Aktiviteten Intervju

Intervjuaktiviteten är en valfri aktivitet med tre komponenter: **Begär tillgänglighet för kandidat**, **schema** och **feedback**. Använd aktiviteten intervju i jobbmallen om du vill inkludera alla kandidaters begäran om tillgänglighet, schema och feedback som en del av en process istället för att använda dem individuellt.

Om du vill inkludera eller begränsa kandidater till detta väljer du ett värde i fältet **Vem du intervjuar**. Tillgängliga alternativ är följande **alla kandidater**, **externa kandidater** och **interna kandidater**. Om du till exempel vill hoppa över interna kandidater i första rundan av intervjun anger du **Vem du intervjuar** till **externa kandidater**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]