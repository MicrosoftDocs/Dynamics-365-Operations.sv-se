---
title: Integrering av anteckning
description: I det här avsnittet beskrivs integreringen av anteckningsdata i dubbel skrivning.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: ed068f4264269334babec9acd59d9d58551333b4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018396"
---
# <a name="note-integration"></a>Integrering av anteckning

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Under affärsprocesser samlar Microsoft Dynamics 365 användare ofta in information om sina kunder. Denna information registreras som aktiviteter och anteckningar. I det här avsnittet beskrivs integreringen av anteckningsdata i dubbel skrivning.

Kundinformation kan klassificeras på följande sätt:

+ **Handlingsbar information som en Dynamics 365-användare hanterar för en kunds räkning** – Till exempel Contoso (en Dynamics 365-användare) genomför ett spelprogram. En av Contosos kunder (en kund) vill delta i programmet. Kunden ber en Contoso-medarbetare att boka en plats i ett spelprogram för dem. Denna reservation sker i Contosos kalender för händelsedeltagaren.
+ **Åtgärdsbar information för en Dynamics 365-användare** – En kund som köper en Surface-enhet anger speciella instruktioner som anger att enheten ska vara gift förpackad före leverans. Instruktionerna är handlingsbar information som ska hanteras av Contoso-medarbetaren som ansvarar för förpackning.
+ **Icke-handlingsbar information** – En kund besöker till exempel Contoso-butiken och uttrycker under sin dialog med en butiksrelation, intresse för *Halo*-spel och speltillbehör. Butikens personal gör en notering om den här informationen. Produktrekommendationsmotorn använder sedan den för att göra rekommendationer till kunden.

I allmänhet fångas handlingsbar information in som *aktiviteter* i Finance and Operations-appar och kundengagemangsappar. Ej handlingsbar information fångas som *anteckningar* i Finance and Operations-appar *kommentarer* i kundengagemangsappar.

> [!TIP]
> Även om noteringar är avsedda för icke-åtgärdsbar information hindrar programmen inte dig från att använda dem för att lagra och hantera åtgärdsbar information om du vill använda dem på det sättet.

Microsoft frisläpper för närvarande funktioner för noteringsintegrering. (Funktioner för aktivitetsintegrering kommer att frisläppas senare.) Noteringsintegreringen är tillgänglig för kunder, leverantörer, försäljningsorder och inköpsorder.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Skapa en notering i en kundengagemangsapp

Följ de här stegen om du vill skapa en notering i en kundengagemangsapp och synkronisera den i Finance and Operations-appen.

1. I kundengagemangsapp, öppna kontopostför en kund.
2. I fönstret **tidslinje** välj plustecknet (**+**) och välj sedan **Anteckning** för att skapa en anteckning.

    ![Skapa en notering i en kundengagemangsapp](media/notes-ce-1.png)

3. Ange en titel och en beskrivning och välj sedan **Lägg till notering**.

    ![Ange en titel och en beskrivning](media/notes-ce-2.png)

    Den nya noteringen läggs till kundens tidslinje.

    ![Ny notering på kundens tidslinje](media/notes-ce-3.png)

4. Logga in på Finance and Operations-appen och öppna samma kundpost. Lägg märke till att knappen **Bilagor** (gemsymbol) i det övre högra hörnet anger att posten har en bifogad fil.

    ![Meddelande om en bilaga](media/notes-ce-4.png)

5. Välj knappen **Bilagor** för att öppna sidan **Bilagor**. Du bör hitta noteringen som du skapade i kundengagemangsappen.

    ![Notering från kundengagemangsapp](media/notes-ce-5.png)

Alla uppdateringar av noteringen synkroniseras fram och tillbaka mellan Finance and Operations-appen och kundengagemangsappen.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Skapa en notering i Finance and Operations-appen

Du kan också skapa en anteckning i en Finance and Operations-app och den kommer att synkroniseras till kundengagemangsappen.

Följ de här stegen om du vill skapa en notering i Finance and Operations och synkroniserad den sedan till en kundengagemangsapp.

1. I Finance and Operations-appen, på sidan **Bilagor**, välj **Ny** \> **notering**.

    ![Skapa en notering i en Finance and Operations-app](media/notes-fo-1.png)

2. Ange en rubrik och en kort uppsättning instruktioner och välj sedan **Spara**.

    ![Ange en titel och instruktioner](media/notes-fo-2.png)

3. Uppdatera posten i kundengagemangsapp. Du bör hitta den nya noteringen under tidslinjen.

    ![Ny notering på tidslinjen i kundengagemangsapp](media/notes-fo-3.png)

Du kan klassificera en notering som intern eller extern.

- I Finance and Operations-app, på sidan **Bilagor**, öppna en anteckning och sedan i fältet **Begränsning** välj **Intern** eller **Extern**.

    ![Begränsningsfält](media/notes-fo-4.png)

Du kan även skapa en URL.

1. I Finance and Operations-appen, på sidan **Bilagor**, välj **Ny** \> **URL**.
2. Ange en titel och en URL.
3. I fältet **Begränsning**, välj **Intern** eller **Extern**.

    ![Skapa en URL i en Finance and Operations-app](media/notes-fo-5.png)

4. Välj **Spara**.

    Eftersom kundengagemangsappar inte har någon URL-typ integreras URL med dubbel skrivning som en notering.

    ![URL visas som en notering i en kundengagemangsapp](media/notes-ce-6.png)

> [!NOTE]
> Filbilagor stöds inte.

## <a name="templates"></a>Mallar

Integrering av anteckning inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Finance and Operations-app | Kundengagemangsapp | beskrivning |
|----------------------------|-------------------------|-------------|
| [Kundbilagor](mapping-reference.md#230) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in kundspecifik information (för både organisationer och personer). |
| [Bilagor till leverantörsdokument](mapping-reference.md#231) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in leverantörsspecifik information (för både organisationer och personer). |
| [Försäljningsorderrubrikens dokumentbilagor](mapping-reference.md#229) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in försäljningsorderspecifik information. |
| [Inköpsorderhuvudets dokumentbilagor](mapping-reference.md#232) | Anteckning | Företag som använder vanlig text och URL-adresser för att samla in inköpsorderspecifik information. |

Mer information finns i [Mappningsreferens för dubbel skrivning](mapping-reference.md).
