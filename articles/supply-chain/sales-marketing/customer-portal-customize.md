---
title: Anpassa och använda kundportalen
description: I det här avsnittet beskrivs hur du anpassar kundportalen efter att den har lagts till i systemet.
author: Henrikan
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 02ad0470b7886b2e9b259682a7f8c8150d656cfb
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063503"
---
# <a name="customize-and-use-the-customer-portal"></a>Anpassa och använda kundportalen

[!include [banner](../includes/banner.md)]


I det här avsnittet beskrivs de olika sidor som medföljer kundportalen. Den förklarar vad sidorna gör och hur du kan anpassa dem.

Kundportalen erbjuder några medföljande webbsidor och åtgärder. I följande webbplatsöversikt finns en översikt över de webbsidor och åtgärder och vilka roller som kan utföra åtgärderna.

![Översikt över kundportalwebbplats.](media/customer-portal-site-map.png "Översikt över kundportal webbplats")

## <a name="typical-customizations"></a>Typiska anpassningar

Följande avsnitt innehåller information om grunderna i Power Apps-portaler och hur du kan anpassa portaler:

- [Arbeta med mallar](/powerapps/maker/portals/work-with-templates) – i det här avsnittet finns en allmän översikt över hur Power Apps-portaler fungerar och hur du kan göra enkla anpassningar av portaler.
- [Hantera portalinnehåll](/dynamics365/portals/manage-portal-content) – i det här avsnittet beskrivs hur du kan hantera och anpassa innehållet som ligger på en portal.
- [Redigera CSS](/powerapps/maker/portals/edit-css) – i det här avsnittet får du hjälp med att göra mer komplexa anpassningar av portalens användargränssnitt.
- [Skapa ett tema för portalen](/dynamics365/portals/create-theme) – i det här avsnittet får du hjälp med att skapa ett användargränssnittstema för portalen.
- [Skapa och exponera portalinnehåll enkelt](/dynamics365/portals/create-expose-portal-content) – i det här avsnittet får du hjälp med att hantera underliggande data och tabeller som du använder för portalen.
- [Konfigurera en kontakt som ska användas på en portal](/powerapps/maker/portals/configure/configure-contacts) – i det här avsnittet beskrivs hur du skapar och anpassar användarroller och hur du arbetar med säkerhet och autentisering i Power Apps-portaler.
- [Konfigurera noteringar för tabellformulär och webbformulär på portaler](/powerapps/maker/portals/configure-notes) – i det här avsnittet beskrivs hur du lägger till dokument och ytterligare lagringsutrymme på portalen.
- [Felhantering för portalens webbplats](/powerapps/maker/portals/admin/view-portal-error-log) – i det här avsnittet beskrivs hur du visar portalens felloggar och lagrar dem i Microsoft Azure Blob Storage-kontot.

## <a name="customize-the-order-creation-process"></a>Anpassa processen för att skapa order

När en användare skickar en order med hjälp av kundportalen, synkroniseras ordern automatiskt till motsvarande Dynamics 365 Supply Chain Management-miljö. Eftersom användaren är en extern kund, döljs vissa nödvändiga uppgifter avsiktligt från dem. Denna information fylls i automatiskt när formuläret skickas.

I det här avsnittet visas hur du bör ställa in kontakter för att undvika fel. Den förklarar fält som ställs in automatiskt och hur du kan ändra värdet på dessa fält om du måste.

### <a name="the-out-of-box-order-creation-process"></a>Den medföljande processen för att skapa order

Här följer de här standardstegen för att skicka en order från kundportalen.

1. På startsidan väljer du panelen **skapa order** för att öppna guiden **Skapa order**.
1. På sidan **Orderinformation** anger du följande fält:

    - **Begärt inleveransdatum** – Ange leveransdatum.
    - **Leveransadress** – Ange den adress som ordern ska levereras till.
    - **Företag** – Välj namnet på kundföretaget. Det här fältet ställs automatiskt in för användare som inte är administratörer.
    - **Rekvisitionsnummer** – Ange orderns rekvisitionsnummer. Detta fält krävs inte.
    - **Leverera till land/region** – ange landet eller regionen som artiklarna ska levereras till. Det här fältet ställs automatiskt in för användare som inte är administratörer.

    ![Sidan Orderinformation.](media/customer-portal-order-information.png "Sidan orderinformation")

1. Välj **Nästa**.
1. På sidan **Artiklar** markerar du **Lägg till artikel**.

    ![Sidan Artiklar.](media/customer-portal-items.png "Sidan artiklar")

1. I dialogrutan **Artikelinformation** anger du följande fält:

    - **Produktnamn** – Sök och välj en produkt som du vill lägga till i ordern.
    - **Kvantitet** – Ange kvantiteten för den valda produkten.
    - **Enhet** – Ange måttenheten (t.ex. **styck**, **kgs** eller **box**).
    - **Uppskattat nettobelopp** – värdet beräknas som det uppskattade priset för artikeln × kvantiteten för den valda enheten.

    ![Dialogruta för artikelinformation.](media/customer-portal-item-information.png "Dialogruta för artikelinformation")

1. Välj **Skicka** för att lägga till artikeln till ordern.
1. Upprepa steg 4 till och med 6 tills du har lagt till alla artiklar som du vill beställa.
1. När du har lagt till alla artiklar väljer du **Nästa** på sidan **Artiklar**.
1. På sidan **Orderinformation** finns en sammanfattning av ordern. Granska orderinnehåll och leveransinformation. Om allting ser korrekt ut väljer du **Skicka** för att skicka ordern.

    ![Sidan Slutförd orderinformation.](media/customer-portal-order-submit.png "Sidan slutförd orderinformation")

### <a name="standard-data-setup"></a>Ställa in standarddata

För att säkerställa en smidig användarupplevelse fyller kundportalen automatiskt i värden för flera obligatoriska fält. Dessa värden baseras på informationen i kontaktposten för den kund som skickar ordern.

För varje [kontaktrad](/powerapps/maker/portals/configure/configure-contacts) som tillhör en kund som kommer att använda kundportalen för att skicka order måste värden anges för följande obligatoriska fält. Annars kommer fel att uppstå.

- **Företag** – Den juridiska personen som ordern tillhör
- **Potentiell kund** – Det kundkonto som är associerat med ordern.
- **Prislista** – den anpassade prislistan för kunden
- **Valuta** – valutan för priset
- **Leverera till land/region** – landet eller regionen som artiklarna ska levereras till

Följande fält ställs automatiskt in för tabellen för försäljningsorder:

- **Språk** – språket för ordern (som standard hämtas värdet från kontaktposten.)
- **Leverera till land/region** – landet eller regionen som artiklarna ska levereras till (som standard hämtas värdet från kontaktposten.)
- **Kontaktperson** – användaren som kan kontaktas för information om ordern (som standard hämtas värdet från kontaktposten.)
- **Företag** – den juridiska person som ordern tillhör (som standard hämtas värdet från kontaktposten.)
- **Potentiell kund** – det kundkonto som är kopplat till ordern (som standard hämtas värdet från kontaktposten.)
- **Fakturakund** – Orderns faktureringskonto (standardvärdet är den potentiella kunden från kontaktposten.)
- **Namn på försäljningsorder** – namnet på försäljningsordern (standardvärdet är **försäljningsorder** .)
- **Valuta** – Valutan för priset (som standard hämtas värdet från kontaktposten.)
- **Prislista** – den anpassade prislistan för kunden (som standard hämtas värdet från kontaktposten.)
- **Beskrivning av leveransadress** – leveransadressen för försäljningsordern (Standardvärdet är **Beskrivning av leveransadress**).

### <a name="modify-the-order-creation-process"></a>Ändra processen för att skapa order

Du kan fritt ändra utseende och användargränssnitt för kundportalen om du inte ändrar den grundläggande processen för att skapa order. Om du vill ändra processen för att skapa order måste du ha några poäng i åtanke.

Ta inte bort följande kolumner från tabellen för försäljningsorder i Microsoft Dataverse eftersom de krävs för att skapa en försäljningsorder i dubbelriktad skrivning:

- **Företag** – Den juridiska personen som ordern tillhör
- **Namn** – Namnet på försäljningsordern
- **Valuta** – valutan för priset
- **Prislista** – den anpassade prislistan för kunden
- **Leverera till land/region** – landet eller regionen som artiklarna ska levereras till
- **Potentiell kund** – Det kundkonto som är associerat med ordern.
- **Språk** – språket för ordern (vanligtvis är språket den potentiella kundens språk.)
- **Beskrivning av leveransadress** – leveransadressen för försäljningsordern

För artiklar krävs följande kolumner:

- **Produkt** – produkten som ska beställas
- **Kvantitet** – kvantiteten för den valda produkten
- **Enhet** – måttenheten (t.ex. **styck**, **kgs** eller **box**)
- **Leverera till land/region** – landet eller regionen för leveransen
- **Beskrivning av leveransadress** – leveransadressen för ordern

Du måste se till att kundportalen inte skickar värden för alla dessa kolumner.

Om du vill lägga till kolumner på sidan eller ta bort kolumner, se [skapa eller redigera snabbregistreringsformulär för en rationaliserad datainmatningsupplevelse](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Om du vill ändra hur kolumnerna är förinställda och hur värden ställs in när sidan sparas, kan du läsa följande information i dokumentationen för Power Apps-portalen:

- [Förifyllt fält](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Ange värde vid sparande](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Anpassa startsidan

Alla kontrollerna i kundportalen är inbyggda i Power Apps-portalkontroller. Du kan anpassa dem genom att följa stegen i dokumentationen [Sammanställ en sida](/powerapps/maker/portals/compose-page)Power Apps-portaler.

Den enda anpassade kontrollen som ingår i kundportalmallen används för att skapa panelerna på startsidan.

![Paneler på startsidan.](media/customer-portal-home-page-tiles.png "Paneler på startsidan")

Gör så här om du vill ändra paneler.

1. Öppna [Portalhanteringsapp](/powerapps/maker/portals/configure/configure-portal).
1. I navigeringsfönstret till vänster, välj **Sidmallar**.

    ![Navigeringsfönster för portalhantering.](media/customer-portal-nav.png "Navigeringsfönster för portalhantering")

1. Markera den sidmall som heter **Start**.
1. I fältet **webbmall** väljer du **start**-länken för att öppna källkoden för den sidan.

    ![Fältet Webbmall.](media/customer-portal-web-template.png "Fältet webbmall")

1. Du bör nu se alla källkoder för startsidan och kan ändra den efter behov.

## <a name="resources"></a>Resurser

Mer information om hur du kan ställa in och anpassa kundportalen finns i följande resurser:

- [Power Apps-portaldokumentation](/powerapps/maker/portals/overview)
- [Dokumentation för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [Om portalens livscykel](/powerapps/maker/portals/admin/portal-lifecycle)
- [Uppgradera en portal](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrera portalkonfiguration](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]