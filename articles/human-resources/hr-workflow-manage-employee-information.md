---
title: Använd arbetsflöden för att hantera medarbetarinformation
description: Detta ämne beskriver hur du kan använda arbetsflöden för att hantera medarbetarinformation.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750745"
---
# <a name="use-workflows-to-manage-employee-information"></a>Använd arbetsflöden för att hantera medarbetarinformation

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.

Arbetsflödeskapaciteten för personal innehåller flera arbetsflöden för hantering av personalaktiviteter. Dessutom finns många alternativ så att du kan ändra särskilda arbetsflöden och koppla dem till en rapporthierarki. Arbetsflöden finns tillgängliga för att hjälpa dig hantera ändringar i flera olika typer av medarbetarinformation. Du kan associera ett arbetsflöde med en befattning. Om sedan medarbetare ändrar sin medarbetarpost startas ett arbetsflöde som måste godkännas innan den nya informationen sparas. Arbetsflöden är fördefinierade för följande typer av information som kan hjälpa dig att effektivt hantera ändringar och behålla medarbetarinformationen korrekt:

-   Identifieringsnummer
-   Kurser
-   Utbildning
-   Bild
-   Lånade objekt
-   Yrkeserfarenhet
-   Projekterfarenhet
-   Kompetenser
-   Förtroendeuppdrag
-   Personalåtgärder
-   Kursregistrering

När medarbetare anställs, överförs eller sägs upp kan arbetsflödet innehålla en granskningsprocess. På så sätt kan ett dokument ändras eller villkoren för en åtgärd definieras som en del av arbetsflödet. När granskningen är klar slutförs dokumentet eller åtgärden och arbetsflödet fortsätter till ett slutligt godkännandesteg.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associera ett arbetsflöde med en befattningshierarki

Du kan associera ett arbetsflöde till vilken positionshierarki som helst som du konfigurerar. Två hierarkityper används för arbetsflödesflöde: **Hanterbar** och **Konfigurerbara**.

- En **Hanterbar** som är chef representerar rapporteringsstrukturen i företaget eller organisationen. Mer information om den här hierarkitypen finns i [Rapporter till position](hr-personnel-positions.md#reports-to-position).
- En **konfigurerbar** hierarki representerar en matris eller en anpassad hierarki. Mer information om den här hierarkitypen finns i [relationer](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Exempel på chefshierarki

Du kan konfigurera ett arbetsflöde så att en begäran skickas till medarbetarens chef och hoppar över den när en medarbetare skickar en inköpsbegäran för en ny dator. När du konfigurerar arbetsflödessteget ställer du in fältet **Tilldelningstyp** på **Hierarki**. Fliken **Hierarkityp** blir då tillgänglig. I det här exemplet väljer du hierarki **Hanterbar**.

### <a name="configurable-hierarchy-example"></a>Exempel på konfigurerbar hierarki

Om en befattning som är kopplad till en matrisrapporteringshierarki kan du konfigurera ett arbetsflöde som vidarebefordrar utgifter för ett specifikt projekt till projektledning i stället för chefen för den medarbetaren. Ange i det här fallet fältet **Tilldelningstyp** som **Hierarki**. Under **Hierarki** väljer du **Konfigurerbar** hierarki. När arbetsflödet har ställts in väljer du hierarkin **Associerade** på sidan **Arbetsflödesinställning** och väljer den hierarki som ska användas för arbetsflödesflödet.

> [!IMPORTANT]
> När ett dokument, en transaktion eller en huvudpost skickas för arbetsflödesgodkännande används den huvudsakliga befattningen för att bestämma vem dokumentet ska skickas till härnäst.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Hierarkiinställning i arbetsflödesparametrar

1. Gå till **Arbetsflödesparametrar**, gå till **Hierarkiflöde**.
2. Som standard är alternativet **Använd befattningshierarki** inställt på **Nej**. I det här fallet används arbetarens primära position i arbetsflödet när den navigerar i hierarkin. Ange alternativet **Ja** om du vill att arbetsflödet ska använda befattningens överordnade när du navigerar i hierarkin.

### <a name="additional-example"></a>Ytterligare exempel 

Medarbetaren Grace Engman har två befattningar: konsult och utbildare. Graces primära befattning är utbildare. När hon inte utbildar nya medarbetare är hon tillgänglig för konsultarbete. Genom sin huvudsakliga befattning rapporterar Grace till Claire, chef för personalavdelningen. Claire rapporterar till Charlie. För sin konsulttjänst har Grace flera relationer med streckade linjer, beroende på projektet.

Grace-företaget skapar arbetsflödesflödesregler som baseras på en **konfigurerbar** hierarki (matris-/projektbaserade hierarkier). I den här hierarkin används Graces konsultposition. Om alternativet **Använd befattningshierarki** är inställt på **Nej**, när ett dokument dirigeras till Grace för hennes godkännande kommer arbetsflödet att titta på hennes primära position (utbildare) för att avgöra vart dokumentet ska dirigeras härnäst. I så fall kommer den först att dirigeras till Claire och sedan till Charlie. Om alternativet är inställt på **Ja** och arbetsflödet använder en **konfigurerbar** hierarki, söker arbetsflödet efter Graces konsultposition och rapporteringsrelationen för att fastställa vart dokumentet ska dirigeras nästa gång.

### <a name="configure-a-human-resources-workflow"></a>Konfigurera personalåtgärdsarbetsflöden
Om du vill konfigurera ett grundläggande arbetsflöde som startas när anställda begär ändringar i sin personliga kod följer du dessa steg.

1.  På sidan **Personalarbetsflöden** väljer du **Ny**.
2.  I listan över tillgängliga arbetsflöden väljer du **ID-nummer**.
3.  Klicka på **Kör** för att öppna arbetsflödesdesignern och sedan ange ditt användarnamn och lösenord.
4.  Flytta elementet **Godkänna identifieringsnummer** från listan med arbetsflödeselement till designerarbetsytan.
5.  Anslut godkännandeelement för **Starta** och **Slutföra**.
6.  Dubbeltryck (eller dubbelklicka) på **Godkänn element**, markera samt håll (eller högerklicka), och välj sedan **Egenskaper**.
7.  Så här lägger du till arbetsuppgiftsinstruktioner:

    1.  Välj **Tilldelning** och välj sedan **Hierarki** under tilldelningstypen.
    2.  Under **Hierarki** väljer du **Konfigurerbar hierarki**.
    3.  Lägg till ett stoppvillkor och stäng sidan.

8.  Slutför ytterligare instruktioner.
9.  Välj **Spara och stäng**. Aktivera det nya arbetsflödet när dialogrutan öppnas och välj **Aktivera**.
10. Gå till **Personal** &gt; **Befattningar** &gt; **Befattningshierarkityper**.
11. Välj **Matris**.
12. Lägg till arbetsflödet **Medarbetares ID-nummer** i listan.

## <a name="additional-resources"></a>Ytterligare resurser

[Visa och hantera adressändringar](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
