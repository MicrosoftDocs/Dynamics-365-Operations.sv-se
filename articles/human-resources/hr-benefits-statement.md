---
title: Förmånsutdrag
description: I rapporten Förmånsutdrag förklaras de förmåner som en medarbetare har registrerats för.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 46f7358684502a4bf05854fbcb5cca9a1eb2c87c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548065"
---
# <a name="benefit-statement"></a>Förmånsutdrag

I rapporten **Förmånsutdrag** ger ett utdrag av de förmåner som en medarbetare har registrerats för. Det går att få åtkomst till rapporten direkt till en medarbetare eller av förmånsadministratören. **Förmånsutdraget** innehåller en lista över medarbetarens registrerade förmåner, disponeringsalternativ, kostnader och alla registrerade anhöriga eller förmånstagare Utdraget kan skrivas ut för en enskild arbetare eller flera arbetare.

> [!NOTE]
Funktionen **förmånsutdrag** måste aktiveras i arbetsytan **funktionshantering**. För att göra detta måste funktionen **förmånshantering** måste vara påslagen i Funktionshantering. 


## <a name="importing-the-benefit-statement"></a>Importera förmånsutdrag 

Du måste importera **förmånsutdrag** med hjälp av rapportkonfigurationen **förmånsutdrag** blir tillgängligt. Det gör du genom att utföra följande steg:

1.  Gå till arbetsytan **Systemadministration**.

2.  Välj panelen **Elektronisk rapportering**.

3.  Gå till **Konfigurationsleverantörer** och välj **Databaser**. 

  ![Välj Databaser.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Välj **Personalresurser** i listan och välj **öppna**.

    ![Konfigurationsdatabaser.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Välj **Modell för förmånsutdrag** i det vänstra fönstret och expandera den så att **Format för förmånsutdrag** visas.

6.  Välj **Format för förmånsutdrag** i det vänstra fönstret.

7.  Till höger om skärmen finns en snabbflik för **versioner**. Välj **Importera**.

    ![Snabbfliken versioner.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Generera förmånsutdraget som en PDF-fil

Som standard skrivs **förmånsutdraget** ut som ett Microsoft Word dokument. Om du vill skriva ut i ett PDF-format måste du konfigurera PDF-alternativet i **destinationen Elektronisk rapportering**. 

1. Det gör du genom att gå till **Arbetsytan för systemadministration** > **Elektronisk rapportering** > **Relaterade länkar** > **Mål för elektronisk rapportering**.

1.  Välj **Ny**.

2.  I fältet **Referenser** väljer du formatet **Format för förmånsutdrag**.

3.  På snabbflikarna **Fildestination** välj **Ny**.

4.  I fältet **namn** anger du **Förmånsutdrag PDF**.

5.  I fältet **Filkomponentnamn** väljer du **Förmånsutdrag**.

6.  Markera kryssrutan **Konvertera till PDF**.

7.  Välj **Inställningar** från menyalternativet. 

    ![Fildestination.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Markera snabbfliken **Fil** och markera sedan **Aktiverad**.

9.  Välj **OK**.
   
> [!NOTE]
> Fördelarhanteringsfunktionen är i ett förhandsgranskningsläge. Det finns ett känt problem när du använder inställningen för e-postdestination i rapporten **Destination för elektronisk rapportering**. Du kan få ett felmeddelande och e-postmeddelandet kommer inte att skickas.

**Förmånsutdraget** kan genereras från följande sidor:

-   **Arbetsyta för förmånshantering** > **Länkar** > **Rapporter** > **Förmånsutdrag**

-   **Medarbetare (äldre formulär)** > **Fliken Personlig information** > **Förmånsutdrag**

-   **Strömlinjeformad medarbetarinmatning** > **Förmånsrapporter** > **Förmånsutdrag**

-   **Självbetjäning för medarbetare** > **Förmåner** > **Visa förmånsutdrag**

> [!NOTE]
>  Åtkomst till **förmånsutdrag** i **Självbetjäning för medarbetare** styrs av behörigheten **Visa förmånsutdrag**. Detta gäller enligt **Förmåner för självbetjäning för medarbetare**. Denna behörighet beviljas till medarbetare som standard.

## <a name="report-contents"></a>Rapportinnehåll

**Förmånsutdraget** skriver ut medarbetarens bekräftade planval, inklusive eventuella avstängda planer. I bilden nedan visas ett exempel på denna rapport. 

![Förmånsutdragsrapport.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

I rapporten visas alternativet **Plan**, **Disponeringsalternativ**, **Medarbetarkostnad** och **Arbetsgivarens kostnad**. Rapporten listar också alla som omfattas av beroende. Om planen har associerats med den, kommer den och deras distributionsprioritet och procent, att visas.

Rapporten **Förmånsutdrag** kan skrivas ut för flera medarbetare samtidigt med hjälp av snabbflikarna **Poster att inkludera** på sidan **Förmånsutdrag**.
