---
title: Tidsplanering av intervjuer och feedback
description: Det här avsnittet innehåller information om intervjuplanering och återrapportering aktiviteter i Attract.
author: ''
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: hasrivas
ms.openlocfilehash: 7bc5a66bb221cb0ab2c69fcb1013ed48a7c664a6
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2019
ms.locfileid: "374982"
---
# <a name="interview-scheduling-and-feedback"></a>Tidsplanering av intervjuer och feedback

[!include[banner](../includes/banner.md)]

## <a name="scheduler-activity"></a>Aktiviteten Schemaläggare

Aktiviteten schemaläggare är valfri och har två komponenter: kandidatens begäran om tillgänglighet och tidsplan. Komponenten kandidaten tillgänglighet kan du använda e-post för att begära den sökandes tillgänglighet. Komponenten schemaläggare ger möjligheten att tidsplanera intervjuer med kandidater och anställningsteamet.

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

    Om **rekommendationer** är markerat kommer visas och intervjurutnätet kommer att vara förifylld. Du kommer att kunna se aktuell i kalendertillgängligheten för alla markerade intervjuare. Du kommer också kunna visa kalendern och om de är en intern kandidaten.

3. Om det finns inga förslag, i kolumnen **intervjuare** väljer du i ett klockslag, ange intervjuntitel, information och fylla i platsinformation efter behov. Kan du inkludera **Skype för företag** för intervjun.

4. Om du vill inkludera ytterligare intervjuare klickar du på rutnätskolumn **Lägg till intervju** att välja en eller flera intervjuare. Du kan använda ellipsalternativet (...) för att ta bort en intervju från slingan.
    
5. Om intervjuerna planeras i en annan tidszon, välj krävd stad/tidszonen från den nedrullningsbara listan i det övre högra hörnet. Intervjuarens tillgänglighetsrutnät uppdateras till den nya tidszonen. Tidszonen som valts visas nu också i vyn **intervjusammanfattning** som delas med intervjuare och kandidaten. 

6. Klicka på **skicka till intervjuare** för att skicka mötesinbjudan till inblandade intervjuare.

    När intervjubegäran skickats till intervjuare kan de svara direkt från e-postinbjudan som de får.

    >[!NOTE]
    > För alla 1:1-intervjuer skickas påminnelser till intervjuare per dygn om intervjuaren inte har svarat (accepterat eller avböjt) begäran om intervju.

    > Det finns inga automatiska påminnelser för begäran om intervju för alla panelintervjuer. För att utlösa en påminnelse manuellt, redigera intervjun och använd alternativet **uppdatera och skicka** för att skicka tillbaka begäran till intervjuare.

    Intervjuarens svar samlas in och visas i Attract. Om intervjuaren tackar nej till inbjudan, meddelas ändringar. För att se svaren i rutnätsvyn **schemaläggare**, klicka på bubbelikonen.

[![Attract rekryterarvy av en intervjuarens svar](./media/schedule-interviewer-response.png)](./media/schedule-interviewer-response.png)

7. När du är klar kan delas med sökande intervjuschemat klickar du på **skicka till kandidaten**. Du kan välja att visa eller dölja intervjuarens namn och platser med sökande.

8. Välj en e-postmall och skicka intervjusammanfattningen till kandidaten. Kandidaten kan visa informationen i deras e-post samt deras kandidatportal.
    
>[!NOTE] 
> Tillgängligheten för en kalender visas endast om kandidaten är intern. Endast en intern kandidat kan ska användas för att förbättra rekommendationer för intervjuschema. Kandidater (intern eller extern) kan för närvarande inte ta emot e-postinbjudningar, istället får kandidaterna endast en sammanfattning av intervjuerna.

## <a name="feedback-activity"></a>Aktiviteten Feedback

Feedbackaktiviteten är valfri i en jobbmall. Denna aktivitet låter intervjudeltagare ange rekommendationer eller feedbackkommentarer för en sökande. Om fältet **Ärv feedbackdeltagare från anställningsteamet** har valts kommer rekryterare, anställande chefer och intervjuare registreras automatiskt i aktiviteten Feedback. Organisationer kan låta intervjuare visa feedback för andra människor innan de skickar sin egen feedback. Organisationer kan även tillåta att intervjuare redigerar deras feedback när de har skickat sina kommentarer. Intervjuare påminns skicka feedback för nyligen gjorda intervjuer utifrån den förinställda konfigurationen som en del av jobbmallen. Anställande chefen eller en rekryterare för jobbet kan också välja att manuellt påminna intervjuaren om att skicka feedback.

## <a name="interview-activity"></a>Aktiviteten Intervju

Intervjuaktiviteten är en valfri aktivitet med tre komponenter: Begär tillgänglighet för kandidat, schema och feedback. Använd intervjuaktiviteten i jobbmallen om du vill att alla kandidaters begäran om tillgänglighet schemalägga. och feedback som en del av processen i stället använder dem individuellt i anställningsprocessen.
