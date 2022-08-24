---
title: Integrering av anteckning
description: I den här artikeln beskrivs integreringen av anteckningsdata i dubbel skrivning.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f09d455181b7929e25d5238949a0236ac60d457b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289029"
---
# <a name="note-integration"></a>Integrering av anteckning

[!include [banner](../../includes/banner.md)]



Under affärsprocesser samlar Microsoft Dynamics 365 användare ofta in information om sina kunder. Denna information registreras som aktiviteter och anteckningar. I den här artikeln beskrivs integreringen av anteckningsdata i dubbel skrivning.

Kundinformation kan klassificeras på följande sätt:

+ **Handlingsbar information som en Dynamics 365-användare hanterar för en kunds räkning** – Exempelvis genomför Contoso (en Dynamics 365-användare) en spelshow. En av Contosos kunder (en kund) vill delta i programmet. Kunden ber en Contoso-medarbetare att boka en plats i ett show-program för dem. Denna reservation sker i Contosos kalender för händelse deltagaren.
+ **Åtgärdsbar information för en Dynamics 365-användare** – En kund som köper en Surface-enhet anger speciella instruktioner som anger att enheten ska vara gift förpackad före leverans. Instruktionerna är åtgärdsbar information som ska hanteras av Contoso-medarbetaren som ansvarar för förpackning.
+ **Icke-åtgärdsbar information** – En kund besöker till exempel Contoso-butiken och uttrycker under sin dialog med en butiksrelation, intresse för *Halo* spel och speltillbehör. Butikens personal gör en notering om den här informationen. Produktrekommendationsmotorn använder sedan den för att göra rekommendationer till kunden.

I allmänhet registreras information som kan ageras på som *aktiviteter* i appar för ekonomi och drift samt kundengagemangsappar. Information som ej kan ageras på registreras som *anteckningar* i appar för ekonomi och drift och som *kommentarer* i kundengagemangsappar.

> [!TIP]
> Även om noteringar är avsedda för icke-åtgärdsbar information hindrar programmen inte dig från att använda dem för att lagra och hantera åtgärdsbar information om du vill använda dem på det sättet.

Microsoft frisläpper för närvarande funktioner för noteringsintegrering. (Funktioner för aktivitetsintegrering kommer att frisläppas senare.) Noteringsintegreringen är tillgänglig för kunder, leverantörer, försäljningsorder och inköpsorder.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Skapa en notering i en kundengagemangsapp

Följ de här stegen om du vill skapa en anteckning i en kundengagemangsapp och sedan synkronisera den med en app för ekonomi och drift.

1. I kundengagemangsapp, öppna kontopostför en kund.
2. I fönstret **tidslinje** välj plustecknet (**+**) och välj sedan **Anteckning** för att skapa en anteckning.

    ![Skapa en notering i en kundengagemangsapp.](media/notes-ce-1.png)

3. Ange en rubrik och en beskrivning och välj sedan **Lägg till notering**.

    ![Ange en rubrik och en beskrivning.](media/notes-ce-2.png)

    Den nya noteringen läggs till kundens tidslinje.

    ![Ny notering på kundens tidslinje.](media/notes-ce-3.png)

4. Logga in på appen för ekonomi och drift, och öppna samma kundpost. Lägg märke till att knappen **Bilagor** (gemsymbol) i det övre högra hörnet anger att posten har en bifogad fil.

    ![Meddelande om en bilaga.](media/notes-ce-4.png)

5. Välj knappen **Bilagor** för att öppna sidan **Bilagor**. Du bör hitta noteringen som du skapade i kundengagemangsappen.

    ![Notering från kundengagemangsappen.](media/notes-ce-5.png)

Alla uppdateringar av anteckningen synkroniseras fram och tillbaka mellan appen för appen för ekonomi och drift och kundengagemangsappen.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Skapa en anteckning i appen för ekonomi och drift

Du kan också skapa en anteckning i en app för ekonomi och drift, och den kommer att synkroniseras med en kundengagemangsapp.

Följ de här stegen om du vill skapa en anteckning i en app för ekonomi och drift, och sedan synkronisera den med en kundengagemangsapp.

1. I appen för ekonomi och drift, på sidan **Bilagor**, väljer du **Ny** \> **Anteckning**.

    ![Skapa en anteckning i appen för ekonomi och drift.](media/notes-fo-1.png)

2. Ange en rubrik och en kort uppsättning instruktioner och välj sedan **Spara**.

    ![Ange en rubrik och instruktioner.](media/notes-fo-2.png)

3. Uppdatera posten i kundengagemangsapp. Du bör hitta den nya noteringen under tidslinjen.

    ![Ny notering på tidslinjen i kundengagemangsappen.](media/notes-fo-3.png)

Du kan klassificera en notering som intern eller extern.

- I appen för ekonomi och drift, på sidan **Bilagor**, öppna en anteckning innan du i fältet **Begränsning** väljer **Intern** eller **Extern**.

    ![Begränsningsfält.](media/notes-fo-4.png)

Du kan även skapa en URL.

1. I appen för ekonomi och drift, på sidan **Bilagor**, väljer du **Ny** \> **URL**.
2. Ange en rubrik och en URL.
3. I fältet **Begränsning**, välj **Intern** eller **Extern**.

    ![Skapa en URL i appen för ekonomi och drift.](media/notes-fo-5.png)

4. Välj **Spara**.

    Eftersom kundengagemangsappar inte har någon URL-typ integreras URL med dubbel skrivning som en notering.

    ![URL visas som en notering i en kundengagemangsappen.](media/notes-ce-6.png)

> [!NOTE]
> Filbilagor stöds inte.

## <a name="templates"></a>Mallar

Integrering av anteckning inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Appar för ekonomi och drift | Kundengagemangsapp | Beskrivning |
|----------------------------|-------------------------|-------------|
| [Kundbilagor](mapping-reference.md#230) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in kundspecifik information (för både organisationer och personer). |
| [Bilagor till leverantörsdokument](mapping-reference.md#231) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in leverantörsspecifik information (för både organisationer och personer). |
| [Försäljningsorderrubrikens dokumentbilagor](mapping-reference.md#229) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in försäljningsorderspecifik information. |
| [Inköpsorderhuvudets dokumentbilagor](mapping-reference.md#232) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in inköpsorderspecifik information. |

## <a name="limitations"></a>Begränsningar

När du har installerat anteckningslösningen kan du inte avinstallera den. 

Mer information finns i [Mappningsreferens för dubbel skrivning](mapping-reference.md).

