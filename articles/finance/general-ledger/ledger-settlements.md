---
title: Redovisningskvittningar
description: Det här avsnittet beskriver hur du använder sidan Redovisningskvittningar för att kvitta redovisningstransaktioner och återföra kvittningar.
author: mikefalkner
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b9279c264294d95c2a06f9614189b26ce8f78566
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826532"
---
# <a name="ledger-settlements"></a>Redovisningskvittningar

[!include [banner](../includes/banner.md)]

Redovisningskvittningar låter dig matcha debet- eller kredittransaktioner i redovisningen och markera dem som kvittade. På så sätt kan du se till att relaterade transaktioner har tagits bort. Du kan också återföra kvittningar om de ändras av misstag.

## <a name="enable-advanced-ledger-settlements"></a>Aktivera avancerade redovisningskvittningar

Sidan för avancerade redovisningskvittningar ger ytterligare möjligheter att filtrera och välja transaktioner. Följ dessa steg om du vill aktivera avancerade redovisningskvittningar.

1. Välj **Redovisning** \> **Redovisningsinställning** \> **Allmänna redovisningsparametrar**. 
2. På fliken **Redovisningskvittningar** anger du alternativet **avancerad redovisningskvittning** till **Ja** för att aktivera funktionen avancerad redovisningskvittning. Sidan för avancerade **redovisningskvittningar** kommer att användas när du väljer **Redovisningskvittningar** i **periodiska uppgifter**. 
3. Du måste ange en lista med konton som ska användas för redovisningskvittningar kontoplan. Listan används för att filtrera listan över transaktioner som visas på sidan **Redovisningskvittningar**. I listan **kontoplan** väljer du en kontoplan och väljer sedan **Ny** för att lägga till nya konton i listan.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Kvitta transaktioner på sidan för avancerade redovisningskvittningar

Om du vill kvitta redovisningstransaktioner följer du dessa steg.

1. Välj **Redovisning** \> **Periodiska uppgifter** \> **Redovisningskvittningar**.
2. Ställ in filtren längst upp på sidan:

    - Markera ett datumintervall eller välj **Datumintervallkod** för att automatiskt fylla i datumintervallet.
    - Ändra bokföringsskiktet efter behov.
    - Om du vill visa redovisningskonto och dimensioner separat, välj en uppsättning av ekonomiska dimensioner.

3. Välj **Visa transaktioner** för att visa alla transaktioner som matchar de filter som du anger och listan över konton som du angav när du ställde in listan med kontoplanen i föregående avsnitt. Om du ändrar något av filtren eller dimensionsuppsättningarna måste du markera **Visa transaktioner** igen.
4. Markera en eller flera rader som du beaktar för kvittning. Värdet på fältet **markerade belopp** längst upp på sidan höjs eller sänks med det totala beloppet på de rader som du har valt.
5. När du är klar med att välja transaktioner väljer du **Markera valda**. En bockmarkering visas i kolumnen **Markerade** för varje transaktion som du markerade. Dessutom ökar eller minskar värdet på fältet **markerade belopp** ovanför rutnätet med det totala beloppet på de rader som du har markerat.
6. När värdet **markerade belopp** är **0** (noll), välj **Kvitta markerade transaktioner**. Status för de markerade transaktionerna uppdateras till **Kvittad**.

## <a name="make-transactions-easier-to-find"></a>Göra det lättare att hitta transaktioner

Sidan **Redovisningskvittningar** innehåller funktioner som gör det lättare att se de transaktioner som behövs för kvittning.

- Knappen **Avmarkera valda** rensar fältet **Markerade** för alla rader som har valts.
- Filtret **Markerade** låter dig filtrera transaktioner utifrån om fältet **Markerade** har markerats eller avmarkerats.
- Filtret **Status** låter dig filtrera transaktioner baserat på om deras status är **Kvittat** eller **Inte kvittat**.
- Knappen **Sortera efter absolut belopp** låter dig sortera beloppen efter absoluta värden, så att du kan gruppera debet och kredit som har samma belopp.

## <a name="reverse-a-settlement"></a>Återföra en kvittning

Du kan återföra en kvittning som har gjorts av misstag.

1. Följ steg 1 till 3 i avsnittet ”Kvitta transaktioner med sidan för avancerade redovisningskvittningar” för att visa transaktionerna som du letar efter.
2. I fältet **Status** markerar du **Kvittad**.
3. Markera en eller flera rader som du beaktar för återföring. Värdet på fältet **markerade belopp** längst upp på sidan höjs eller sänks med det totala beloppet på de rader som du har valt.
4. När du är klar med att välja transaktioner väljer du **Markera valda**. En bockmarkering visas i kolumnen **Markerade** för varje transaktion som du markerade. Dessutom ökar eller minskar värdet på fältet **markerade belopp** längst upp på rutnätet med det totala beloppet på de rader som du har markerat.
5. När värdet **markerade belopp** är **0** (noll), välj **Återför markerade transaktioner**. Status för de markerade transaktionerna uppdateras till **Inte kvittad**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Uppdatera listan över konton som ingår i transaktionslistan

Välj **Konton för redovisningskvittning** för att öppna en dialogruta där du kan redigera de konton som ingår i listan över transaktioner. Välj **Ny** om du vill lägga till en ny bild i listan. Listan används för att filtrera listan över transaktioner som visas på sidan **Redovisningskvittningar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]