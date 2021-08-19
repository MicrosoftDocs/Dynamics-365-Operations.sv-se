---
title: Skapa juridiska personer
description: I det här avsnittet beskrivs hur du skapar juridiska personer i Microsoft Dynamics 365 Commerce, som måste skapas och konfigureras innan kanaler skapas.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bc5f097a7f941dfa05f4011d9be5caffbb7f01b5f6e67cd7535ef3d1b13f59fe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740441"
---
# <a name="create-legal-entities"></a>Skapa juridiska personer

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar juridiska personer i Microsoft Dynamics 365 Commerce, som måste skapas och konfigureras innan kanaler skapas.

En juridisk person är en organisation som har en registrerad eller lagstiftad juridisk struktur. Juridiska personer kan ingå juridiska kontrakt och måste förbereda utdrag som rapporterar deras resultat.

Ett företag är en sorts juridisk person. För närvarande är företag den enda typ av juridisk person som du kan skapa, och varje juridisk person associeras med ett företags-ID. Denna koppling finns eftersom vissa funktionella områden i programmet använder ett företags-ID eller *DataAreaId*, i deras datamodeller. I dessa funktionella områden används företag som en gräns för datasäkerhet. Användarna kan endast komma åt data för de företag som de är inloggade på. 

När du skapar en kanal måste du ange vilken juridisk person som kanalen tillhör.

## <a name="create-a-new-legal-entity"></a>Skapa ny juridisk person

Om du vill skapa en ny juridisk enhet i Dynamics 365 Commerce, följ dessa steg:

1. I navigeringsfönstret, gå till **Moduler \> Administrationsinställning \> Juridiska personer**.
1. Klicka på **Ny** i åtgärdsfönstret. Fönstret **Ny juridisk person** visas till höger.
1. I fältet **Namn** anger du ett värde.
1. I fältet **Företag** anger du ett värde.
1. Ange eller välj ett värde i fältet **Land/region**.
1. Välj **OK**. 

   ![Skapa en juridisk person.](media/legal-entities.png)

1. I avsnittet **allmän** ge följande information om juridiska personen: 
   1. Ange ett söknamn, om ett söknamn krävs. En söknamn är ett alternativt namn som kan användas för att söka efter den här juridisk person. 
   1. Markera om den här juridisk person används som ett konsolideringsföretag.
   1. Markera om den här juridisk person används som ett elimineringsföretag. 
   1. Välj **systemspråk** för entiteten. 
   1. Välj **tidszon** för entiteten.
1. I avsnittet **Adresser**, klicka på **Redigera** för att ange adressinformation, till exempel gatunamn och nummer, postnummer och ort.
1. Ange information om metoder för kommunikationen till exempel e-postadresser, telefonnummer, webbadress, i avsnittet **Kontaktinformation**.
1. Ange registreringsnumren som används för lagstadgad rapportering i avsnittet **Rapportering enligt lag**.
1. I avsnittet **Registreringsnummer**, ange vilken information som krävs av den juridiska personen.
1. Ange bankkonton och organisationsnummer för juridiska personen i avsnittet **Bankkontoinformation**.
1. Ange leveransinformation för juridiska personen i avsnittet **Utrikeshandel- och logistik**.
1. I avsnittet **Nummerserie**, kan du visa de nummerserier som är kopplade till juridiska personen. Detta kommer att vara tomt att börja med.
1. I avsnittet **Instrumentpanelsbild** kan du visa eller ändra logotyp- och/eller instrumentpanelbilden som associeras med juridiska personen.
1. Ange registreringsnumren som används för att rapportera till skattemyndigheten i avsnittet **Momsregistrering**.
1. Ange 1099-information för juridiska personen i avsnittet **Skatt 1099**.
1. I avsnittet **Momsinformation** ange den juridiska enhetens momsinformation.
1. Välj **Spara**.

I bilden nedan visas ett detaljer för exempel på en juridisk enhet.

![Allmänt avsnitt om juridisk person.](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Ytterligare resurser

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planera en organisationshierarki](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Organisationshierarkier](channels-org-hierarchies.md)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
