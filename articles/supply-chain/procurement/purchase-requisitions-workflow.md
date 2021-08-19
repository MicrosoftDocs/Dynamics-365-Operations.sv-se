---
title: Arbetsflöde för inköpsrekvisitioner
description: Arbetsflödesprocessen flyttar inköpsrekvisitionerna genom granskningsprocessen, från en ursprunglig status för Utkast till statusen Godkänd. När en inköpsrekvisition skickas in för granskning, startas arbetsflödesprocessen. När en inköpsrekvisition har godkänts, kan en inköpsorder skapas för inköpsrekvisitionsraderna och skickas till leverantören för uppfyllelse av ordern.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c512fff1c20fbe539e98a6da02a9a4362c3753b0897b48ee5c6a785d8893bbe9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717248"
---
# <a name="purchase-requisition-workflow"></a>Arbetsflöde för inköpsrekvisitioner

[!include [banner](../includes/banner.md)]

Arbetsflödesprocessen flyttar inköpsrekvisitionerna genom granskningsprocessen, från en ursprunglig status för Utkast till statusen Godkänd. När en inköpsrekvisition skickas in för granskning, startas arbetsflödesprocessen. När en inköpsrekvisition har godkänts, kan en inköpsorder skapas för inköpsrekvisitionsraderna och skickas till leverantören för uppfyllelse av ordern.

Innan en inköpsrekvisition kan skickas för granskning måste arbetsflödet konfigureras. Arbetsflödesprocessen kan innehålla en eller flera granskningssteg i valfri ordning. Arbetsflödesprocessen kan också konfigureras om du vill hoppa över granskningsuppgifterna och om du automatiskt vill godkänna inköpsrekvisitionen. Du kan konfigurera arbetsflödet för att skicka inköpsrekvisitionen som ett enda dokument, eller så kan du skicka enskilda inköpsrekvisitionsrader till lämpliga granskare. Du kan också skapa ett scenario där inköpsrekvisitionen skickas som ett enda dokument till några granskare, och markerade inköpsrekvisitionsrader skickats till andra granskare.  

Om inköpsrekvisitionsraderna granskas individuellt, måste granskningsprocessen slutföras för alla inköpsrekvisitionsrader innan arbetsflödet kan flytta till nästa steg i processen, och innan granskningen av inköpsrekvisitionen som helhet kan slutföras. När granskningen har slutförts för inköpsrekvisitionen, inklusive alla rader, uppdateras övergripande status för inköpsrekvisitionen till **Godkänd**  

Du kan konfigurera ditt arbetsflöde så att den avspeglar affärsprocessen för inköpsrekvisitioner i den aktuella organisationen. Ta hänsyn till följande frågor när du konfigurerar arbetsflödesprocessen för inköpsrekvisitioner:

-   Vilka utgifter måste granskas?
-   Vilka utgifter kan godkännas automatiskt?
-   Vem måste granska och godkänna omkostnadsförfrågningar? Vilken roll är dessa användare tilldelad?
-   Vilken process måste följas om en granskare inte är tillgänglig?

I följande exempel visas två sätt att kan konfigurera arbetsflödet för inköpsrekvisitioner.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Exempel 1: Skicka en inköpsrekvisition som ett enda dokument för granskning
I bilden nedan visas hur en inköpsrekvisition kan flöda genom arbetsflödesgranskningsprocessen som ett enda dokument. Raderna på inköpsrekvisitionen skickas inte individuellt. Följande roller ingår i arbetsflödesprocessen för det här exemplet:

-   **Beställare** – Den användare som begär artiklarna eller tjänsterna. Beställaren kan förbereda inköpsrekvisitionen, eller en annan anställd kan förbereda inköpsrekvisitionen på uppdrag beställaren. Den medarbetaren kallas för förberedare. Förberedaren ansvarar för att hantera inköpsrekvisitionen genom hela granskningen. Det är bara förberedaren av inköpsrekvisitionen som kan ändra den.

**Obs!** En anställd måste beviljas rätt behörighet för att kunna skapa en inköpsrekvisition för någon annans räkning. Använd sidan **Behörighet för inköpsrekvisition** för att ställa in dessa behörigheter.

-   **Inköpsagent** – Användaren som genomför en anskaffningsgranskning och kan godkänna dokumentet.
-   **Beställarens chef** – Användaren som genomför en chefsgranskning och kan godkänna dokumentet.

![Granskningsprocess för arbetsflödet för inköpsrekvisitioner.](./media/purchreqworkflowoverview_submission.gif)  
I det här exemplet innehåller arbetsflödesprocessen för inköpsrekvisitionen följande steg:

1.  Förberedaren skickar inköpsrekvisitionen för granskning.
2.  Inköpsagenten får ett meddelande. Inköpsagenten får ett meddelande som begär att inköpsagenten verifierar informationen i inköpsrekvisitionen. Om obligatorisk information saknas, kan inköpsagenten lägga till den information eller returnera inköpsrekvisitionen till förberedaren som ska lägga till den. När de obligatoriska fälten har fyllts i, kan inköpsrekvisitionsraden flytta till nästa steg i godkännandeprocessen.
3.  Beställarens chef granskar inköpsrekvisitionen. Inköpsrekvisitionen kan skickas till beställarens chef om till exempel beloppet på inköpsrekvisitionen överstiger beställarens utgiftsgräns för inköpsrekvisitioner. Beställarens chef kan godkänna eller avvisa inköpsrekvisitionen, eller returnera till den till förberedaren för ändringar.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Exempel 2: Skicka de enskilda raderna på inköpsrekvisitionen för granskning
I bilden nedan visas hur de enskilda raderna på inköpsrekvisitionen kan skickas via arbetsflödet. Processen för varje rad är vanligtvis samma som processen för en inköpsrekvisition som ska granskas som ett enda dokument. Varje rad måste emellertid gå igenom arbetsflödesprocessen var för sig, innan arbetsflödet kan slutföras för inköpsrekvisitionen som helhet.  

I det här exemplet registrerar en anställd en beställning av affischer och t-tröjor för en marknadsföringskampanj. Kostnaden för affischerna delas mellan marknadsavdelningen och försäljningsavdelningen. Om kostnaden för affischerna eller t-tröjorna överskrider den auktoriserade signeringsgänsen för avdelningschefer, måste inköpsrekvisitionen också granskas av gruppchefen.  

Följande roller ingår i arbetsflödesprocessen för det här exemplet:

-   **Beställare** – Den användare som begär artiklarna eller tjänsterna. Beställaren kan förbereda inköpsrekvisitionen, eller en annan anställd kan förbereda inköpsrekvisitionen på uppdrag beställaren. Den medarbetaren kallas för förberedare. Förberedaren ansvarar för att hantera inköpsrekvisitionen genom hela granskningen. Det är bara förberedaren av inköpsrekvisitionen som kan ändra den.

**Obs!** En anställd måste beviljas rätt behörighet för att kunna skapa en inköpsrekvisition för någon annans räkning. Använd sidan **Behörighet för inköpsrekvisition** för att ställa in dessa behörigheter.

-   **Inköpsagent** – Användaren som genomför en anskaffningsgranskning och kan godkänna dokumentet.
-   **Beställarens chef** – Användaren som genomför en chefsgranskning och kan godkänna dokumentet.
-   **Avdelningschef** – Användaren som genomför en omkostnadsgranskning och kan godkänna dokumentet.
-   **Gruppchef** – Användaren som utför en auktoriserad signeringsgranskning och kan godkänna dokumentet.

![Granskningsprocess av arbetsflödet för inköpsrekvisitionsrader.](./media/purchreqlineworkflowoverview.gif)  
I det här exemplet innehåller arbetsflödesprocessen för inköpsrekvisitionsraderna följande steg:

1.  Förberedaren skickar inköpsrekvisitionen för granskning. Varje rad skickas till granskaren som är konfigurerad att få den i arbetsflödesprocessen.
2.  Inköpsagenten får ett meddelande. Inköpsagenten får ett meddelande som begär att inköpsagenten verifierar informationen i inköpsrekvisitionen och på inköpsrekvisitionsraderna. När inköpsrekvisitionen öppnas av inköpsagenten visas alla rader, men en visuell indikator visar vilka rader som har skickats till inköpsagenten för granskning. Om obligatorisk information saknas, kan inköpsagenten lägga till den information eller returnera inköpsrekvisitionen till förberedaren som ska lägga till den. När de obligatoriska fälten har fyllts i, kan inköpsrekvisitionsraden flytta till nästa steg i godkännandeprocessen. Inköpsrekvisitionsrader kan fortsätta genom granskningen oberoende av varandra.
3.  Beställarens linjechef granskar och godkänner inköpsrekvisitionsraderna. Godkännandet kan skickas till beställarens chef om till exempel beloppet på inköpsrekvisitionsraden överstiger beställarens utgiftsgräns för inköpsrekvisitionsrader. Chefen kan godkänna eller avvisa en eller båda rader i inköpsrekvisitionen.
4.  Avdelningschefen för marknadsavdelningen granskar inköpsrekvisitionsraderna för både affischerna och t-tröjorna. Försäljningsavdelningschefen granskar inköpsrekvisitionsraden endast för affischerna, eftersom det är den enda kostnad som debiteras försäljningsavdelningen.
5.  Gruppchefen granskar och godkänner inköpsrekvisitionsraden för T-tröjor, bara om gruppchefgodkännande krävs om t.ex. beloppet på inköpsrekvisitionsraden överskrider avdelningschefens godkännandegräns. Gruppchefen behöver inte godkänna inköpsrekvisitionsraden för affischerna.

> [!NOTE]
> Systemvalutan måste anges om huvudarbetsflödet för en inköpsrekvisition kräver godkännanden som rör signeringsbegränsningar.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Konfigurera av arbetsflöde för inköpsrekvisitioner
Om du vill skicka en inköpsrekvisition för granskning måste du konfigurera arbetsflödesprocesser för inköpsrekvisitioner. Arbetsflödesprocessen som du definierar styr samspelet mellan användaren som beställer artiklarna (beställaren) och granskaren och godkännaren i arbetsflödet. Flödet för inköpsrekvisitionen beror på villkoren som anges i arbetsflödeskonfigurationen. Till exempel bestämmer dessa kriterier, när inköpsrekvisitionen ska skickas, användaren eller rollen som den ska flödas till och åtgärder som användarna kan vidta.  

I exemplen i det här avsnittet beskrivs hur en inköpsrekvisition kan skickas via arbetsflöde som ett enda dokument eller som enskilda inköpsrekvisitionsrader. Du kan även konfigurera arbetsflödet för att inköpsrekvisitioner för att återspegla intern kontrollgranskningen av inköpsrekvisitioner som har definierats för din organisation.  

Deltagarna eller att granskarna som en uppgift har tilldelats in ett arbetsflöde, kan vara medlemmar i en viss användargrupp, användare som har en viss säkerhetsroll, användare som är kopplade till avsändaren i en ledarskapshierarki, eller namngivna användare eller användare som har specifika omkostnadansvarsområden.

### <a name="purchase-requisition-expenditure-reviewers"></a>Omkostnadsgranskare för inköpsrekvisition

Du kan ställa in omkostnadgranskarekonfigurationer att dynamiskt skicka utgifter för granskning baserat på den användare som tilldelas en projektroll eller en ekonomisk dimension, där omkostnaden debiteras. Arbetsflödeprocessen använder den angivna ägaren av projektrollen eller ekonomiska dimensionen för att bestämma vem skicka omkostnaden till.  

Du kan definiera en eller flera omkostnadgranskarekonfigurationer och välj sedan en konfiguration, när du skapar ett arbetsflöde. Du kan konfigurera omkostnadgranskarevärdena för varje juridisk person i din organisation. När du har definierat omkostnadgranskarekonfigurationerna, tilldelar du konfigurationen i din arbetsflödeuppgift.  

Det är inte nödvändigt att ställa in en omkostnadsgranskarkonfigurationen. Du kan istället tilldela en viss användare eller användargrupp som granskare, när du definierar arbetsflöde. Om du har en komplex organisation, kan angivna omkostnadgranskare öka effektiviteten hos din godkännandeprocess. Dessutom, om du ställer in omkostnadgranskare, behöver du inte uppdatera arbetsflödegranskaretilldelningar varje gång en granskare ändrar jobbroller.  

Du kan ställa in omkostnadgranskarna på sidan **Inköpsrekvisitionomkostnadgranskare**. När du skapar en omkostnadgranskarekonfiguration, måste du ange standardvärden för varje juridisk person som angetts för din organisation. För rekvisitioner som tilldelats ett projekt, kan du ange rollen som ansvarar för att granska rekvisitioner: Projektledare,Projektstyrenhet eller Projektförsäljningchef. Expenditures skickas till användaren som tilldelats den angivna roll. Du kan också skicka omkostnaden för den ekonomiska dimensionägaren, genom att välja lämpligt alternativ för ekonomisk dimension på fliken **Organisationsfördelningar**.  

Om du vill använda en av omkostnadgranskarna, som ställs in i ett arbetsflöde måste du ange alternativet **Typ av deltagare** till **Deltagare vid omkostnad** i egenskaperna **Tilldelning** för det relevanta arbetsflödeselementet.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en rekvisition för förbrukning](tasks/create-requisition-consumption.md)

[Definiera affärsprocessarbetsflöden för inköpsrekvisitioner](https://www.microsoft.com/download/details.aspx?id=101821)

[Anskaffnings- och källarbetsflöden](procurement-sourcing-workflows.md)

[Översikt över inköpsrekvisition](purchase-requisitions-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]