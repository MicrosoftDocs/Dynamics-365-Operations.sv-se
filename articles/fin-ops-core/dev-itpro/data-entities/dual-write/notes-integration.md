---
title: Integrering av anteckning
description: I den här artikeln beskrivs integreringen av anteckningsdata i dubbel skrivning.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8e1444aa311bb2dc74705a3791e58c3187ecd8ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876727"
---
# <a name="note-integration"></a>Integrering av anteckning

[!include [banner](../../includes/banner.md)]



Under affärsprocesser samlar Microsoft Dynamics 365 användare ofta in information om sina kunder. Denna information registreras som aktiviteter och anteckningar. I den här artikeln beskrivs integreringen av anteckningsdata i dubbel skrivning.

Kundinformation kan klassificeras på följande sätt:

+ **Handlingsbar information som en Dynamics 365-användare hanterar för en kunds räkning** – Exempelvis genomför Contoso (en Dynamics 365-användare) en spelshow. En av Contosos kunder (en kund) vill delta i programmet. Kunden ber en Contoso-medarbetare att boka en plats i ett show-program för dem. Denna reservation sker i Contosos kalender för händelse deltagaren.
+ **Åtgärdsbar information för en Dynamics 365-användare** – En kund som köper en Surface-enhet anger speciella instruktioner som anger att enheten ska vara gift förpackad före leverans. Instruktionerna är åtgärdsbar information som ska hanteras av Contoso-medarbetaren som ansvarar för förpackning.
+ **Icke-åtgärdsbar information** – En kund besöker till exempel Contoso-butiken och uttrycker under sin dialog med en butiksrelation, intresse för *Halo* spel och speltillbehör. Butikens personal gör en notering om den här informationen. Produktrekommendationsmotorn använder sedan den för att göra rekommendationer till kunden.

I allmänhet fångas handlingsbar information in som *aktiviteter* i Ekonomi och Drift-appar och kundengagemangsappar. Ej handlingsbar information fångas som *anteckningar* i Ekonomi och Drift-appar *kommentarer* i kundengagemangsappar.

> [!TIP]
> Även om noteringar är avsedda för icke-åtgärdsbar information hindrar programmen inte dig från att använda dem för att lagra och hantera åtgärdsbar information om du vill använda dem på det sättet.

Microsoft frisläpper för närvarande funktioner för noteringsintegrering. (Funktioner för aktivitetsintegrering kommer att frisläppas senare.) Noteringsintegreringen är tillgänglig för kunder, leverantörer, försäljningsorder och inköpsorder.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Skapa en notering i en kundengagemangsapp

Följ de här stegen om du vill skapa en notering i en kundengagemangsapp och synkronisera den i Ekonomi och Drift-appen.

1. I kundengagemangsapp, öppna kontopostför en kund.
2. I fönstret **tidslinje** välj plustecknet (**+**) och välj sedan **Anteckning** för att skapa en anteckning.

    ![Skapa en notering i en kundengagemangsapp.](media/notes-ce-1.png)

3. Ange en rubrik och en beskrivning och välj sedan **Lägg till notering**.

    ![Ange en rubrik och en beskrivning.](media/notes-ce-2.png)

    Den nya noteringen läggs till kundens tidslinje.

    ![Ny notering på kundens tidslinje.](media/notes-ce-3.png)

4. Logga in på Ekonomi och Drift-appen och öppna samma kundpost. Lägg märke till att knappen **Bilagor** (gemsymbol) i det övre högra hörnet anger att posten har en bifogad fil.

    ![Meddelande om en bilaga.](media/notes-ce-4.png)

5. Välj knappen **Bilagor** för att öppna sidan **Bilagor**. Du bör hitta noteringen som du skapade i kundengagemangsappen.

    ![Notering från kundengagemangsappen.](media/notes-ce-5.png)

Alla uppdateringar av noteringen synkroniseras fram och tillbaka mellan Ekonomi och Drift-appen och kundengagemangsappen.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Skapa en anteckning i Ekonomi och Drift-app

Du kan också skapa en anteckning i en Ekonomi och Drift-app och den kommer att synkroniseras till kundengagemangsappen.

Följ de här stegen om du vill skapa en notering i en Ekonomi och Drift-app och synkronisera den i kundengagemangsapp.

1. I Ekonomi och Drift-appen, på sidan **Bilagor**, välj **Ny** \> **Notering**.

    ![Skapa en anteckning i Ekonomi och Drift-app.](media/notes-fo-1.png)

2. Ange en rubrik och en kort uppsättning instruktioner och välj sedan **Spara**.

    ![Ange en rubrik och instruktioner.](media/notes-fo-2.png)

3. Uppdatera posten i kundengagemangsapp. Du bör hitta den nya noteringen under tidslinjen.

    ![Ny notering på tidslinjen i kundengagemangsappen.](media/notes-fo-3.png)

Du kan klassificera en notering som intern eller extern.

- I Ekonomi och Drift-app, på sidan **Bilagor**, öppna en anteckning och sedan i fältet **Begränsning** välj **Intern** eller **Extern**.

    ![Begränsningsfält.](media/notes-fo-4.png)

Du kan även skapa en URL.

1. I Ekonomi och Drift-appen, på sidan **Bilagor**, välj **Ny** \> **URL**.
2. Ange en rubrik och en URL.
3. I fältet **Begränsning**, välj **Intern** eller **Extern**.

    ![Skapa en URL i Ekonomi och Drift-app.](media/notes-fo-5.png)

4. Välj **Spara**.

    Eftersom kundengagemangsappar inte har någon URL-typ integreras URL med dubbel skrivning som en notering.

    ![URL visas som en notering i en kundengagemangsappen.](media/notes-ce-6.png)

> [!NOTE]
> Filbilagor stöds inte.

## <a name="templates"></a>Mallar

Integrering av anteckning inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Ekonomi och Drift-appar | Kundengagemangsapp | Beskrivning |
|----------------------------|-------------------------|-------------|
| [Kundbilagor](mapping-reference.md#230) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in kundspecifik information (för både organisationer och personer). |
| [Bilagor till leverantörsdokument](mapping-reference.md#231) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in leverantörsspecifik information (för både organisationer och personer). |
| [Försäljningsorderrubrikens dokumentbilagor](mapping-reference.md#229) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in försäljningsorderspecifik information. |
| [Inköpsorderhuvudets dokumentbilagor](mapping-reference.md#232) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in inköpsorderspecifik information. |

## <a name="limitations"></a>Begränsningar

När du har installerat anteckningslösningen kan du inte avinstallera den. 

Mer information finns i [Mappningsreferens för dubbel skrivning](mapping-reference.md).
