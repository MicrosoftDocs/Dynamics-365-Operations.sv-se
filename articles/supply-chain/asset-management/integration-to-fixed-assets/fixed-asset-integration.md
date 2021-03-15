---
title: Integrera tillgångshantering med anläggningstillgångar
description: I det här avsnittet beskrivs hur du integrerar modulerna för Tillgångshantering och Anläggningstillgångar så att du kan koppla anläggningstillgångar med underhållstillgångar.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 879950b9aeb345fcd59dfe73d3963a44607c7ac2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994239"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Integrera tillgångshantering med anläggningstillgångar

[!include [banner](../../includes/banner.md)]

Genom att integrera modulerna **Tillgångshantering** och **Anläggningstillgångar** kan du koppla anläggningstillgångar med underhållstillgångar. Användare av anläggningstillgångar kan sedan skapa en underhållstillgång från en ny eller befintlig anläggningstillgång och användare av tillgångshantering kan associera en underhållsanläggning med en befintlig anläggningstillgång. Den här funktionen gör det också enkelt för användare med anläggningstillgångar att visa kostnader som har bokförts från arbetsorder för relaterade underhållstillgångar.

> [!NOTE]
> I det här avsnittet *underhållstillgångar* hänvisar till tillgångar från modulen **tillgångshantering** och *anläggningstillgångar* hänvisar till tillgångar från modulen **anläggningstillgångar**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Ange en standardplats för nya underhållstillgångar som skapas från anläggningstillgångar (valfritt)

Denna valfria konfiguration låter dig ange en funktionell standardplats för nya underhållstillgångar som skapas från anläggningstillgångar. Den här konfigurationen är vanligtvis bara en gång om du slutför hela.

Om du vill slutföra konfigurationen, gör följande.

1. Gå till **Tillgångshantering \> Inställningar \> Parametrar för tillgångshantering**.
1. På fliken **Anläggningstillgångar** i fältet **funktionsplats** väljer du standardplats.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Arbeta med integrerade underhållstillgångar och anläggningstillgångar

Det här avsnittet innehåller en samling procedurer som visar olika sätt som du kan arbeta med integrerad tillgångshantering och funktioner för anläggningstillgångar.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Associera en befintlig underhållstillgång med en anläggningstillgång

Gör följande för att associera en befintlig underhållstillgång med en anläggningstillgång.

1. Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).
1. Välj en tillgång.
1. På snabbfliken **Anläggningstillgångar** i fältet **Nummer för anläggningstillgång**, välj en befintlig anläggningstillgång.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Visa anläggningstillgången som är kopplad till en vald underhållstillgång

Om du vill visa anläggningstillgången som är kopplad till en vald underhållstillgång, följ dessa steg.

1. Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).
1. Välj en tillgång.
1. På snabbfliken **Anläggningstillgångar** i fältet **Nummer för anläggningstillgång**, välj länken.

    Sidan **anläggningstillgångar** för den valda tillgången öppnas. (Vanligtvis finns den här sidan på **anläggningstillgångar \> anläggningstillgångar \> anläggningstillgångar**.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Visa underhållstillgången som är kopplad till en vald anläggningstillgång

Om du vill visa underhållstillgången som är kopplad till en vald anläggningstillgång, följ dessa steg.

1. Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
1. Välj en tillgång.
1. I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Vy** väljer du **underhållstillgång**.

    Sidan **underhållstillgång** för den tillgång som är kopplad till en vald anläggningstillgång öppnas. (Vanligtvis finns den här sidan på **Tillgångshantering \> Tillgångar \> Alla tillgångar**.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Visa underhållskostnader som är associerade med en anläggningstillgång

Arbetsorder för tillgångshantering kan bokföras för underhållstillgångar och varje arbetsorder har normalt en kostnad. När en anläggningstillgång är kopplad med en underhållstillgång kan du gå direkt från anläggningstillgången för att visa relaterade kostnader.

Om du vill visa underhållskostnad som är kopplad till en anläggningstillgång, följ dessa steg.

1. Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
1. Välj en tillgång.
1. I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Vy** väljer du **underhållskostnad**.

    Sidan **underhållskostnad** öppnas och visar relaterade kostnader.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Skapa en ny underhållstillgång för en befintlig anläggningstillgång

För att skapa en ny underhållstillgång för en befintlig anläggningstillgång följer du stegen nedan.

1. Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
1. Välj en tillgång.
1. I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Ny** väljer du **Skapa underhållstillgång**. (Om det här alternativet inte är tillgängligt kanske en underhållstillgång redan är kopplad till den valda anläggningstillgången.)
1. Slutför skapandet av tillgången såsom beskrivs i [Skapa en tillgång](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Skapa en ny anläggningstillgång och lägg till en ny underhållstillgång för den

För att skapa en ny anläggningstillgång och lägga till en ny underhållstillgång för den följer du stegen nedan.

1. Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Slutför skapandet av anläggningstillgången såsom beskrivs i [Skapa en anläggningstillgång](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Ny** väljer du **Skapa underhållstillgång**.
1. Slutför skapandet av tillgången såsom beskrivs i [Skapa en tillgång](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Ta bort kopplingen mellan två resurser

I vissa fall måste du kanske avassociera en underhållstillgång från anläggningstillgången. Om du till exempel vill [skapa en ny underhållstillgång](#new-maintenance-from-fixed) från en anläggningstillgång, måste du först ta bort alla befintliga associationer.

Följ dessa steg för att ta bort en befintlig koppling mellan en underhållstillgång och en anläggningstillgång.

1. Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).
1. Hitta och öppna anläggningstillgången.
1. På snabbfliken **anläggningstillgång** avmarkerar du värdet från fältet **funktionsplats**.
1. Klicka på **Spara** i åtgärdsfönstret.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]