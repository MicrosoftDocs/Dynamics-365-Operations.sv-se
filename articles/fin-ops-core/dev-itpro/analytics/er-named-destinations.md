---
title: Konfigurera postspecifika ER-destinationer för utskriftshantering
description: Detta ämne beskriver hur du konfigurerar postspecifika destinationer för utskriftshantering för ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413617"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Konfigurera postspecifika ER-destinationer för utskriftshantering

[!include [banner](../includes/banner.md)]

Detta ämne förklarar hur en användare med rollen Systemadministratör eller Kundreskontraansvarig kan utföra följande uppgifter:

- Konfigurera namngivna destinationer för [elektronisk rapportering (ER)](general-electronic-reporting.md) för en ER-lösning som genererar fritextfakturor.
- Tilldela en ER-destination till en enda [utskriftshanteringspost](document-reporting-services.md).

Procedurerna kan slutföras i USMF-företaget. Ingen kod behövs.

## <a name="introduction"></a>Introduktion

Du kan konfigurer [destinationer](electronic-reporting-destinations.md) för respektive mapp i filutdatakomponentenr för en ER-[format](general-electronic-reporting.md#FormatComponentOutbound)[konfiguration](general-electronic-reporting.md#Configuration) som används för att generera ett utgående dokument. När du kör ett ER-format av den här typen och du har rätt åtkomstbehörighet kan också ändra de konfigurerade destinationsinställningarna vid körning.

I Microsoft Dynamics 365 Finance **version 10.0.17 och senare** kan en åtgärdskod [konfigureras](er-apis-app10-0-17.md) så att ett ER-format kan ange den åtgärd som användare utför genom att köra det ER-formatet. I modulen **Kundreskontra** kan du, bland inställningarna för utskriftshantering, välja ett ER-format som genererar ett specifikt affärsdokument, till exempel en fritextfaktura. Du kan sedan välja **Vy** om du vill förhandsgranska fakturan eller **Skriv ut** om du vill skicka den till en skrivare. Om en åtgärd överförs för det körande ER-formatet vid körning kan du [konfigurera olika ER-destinationer för olika användaråtgärder](er-action-dependent-destinations.md)..

I Finance-**version 10.0.21 och senare** kan en namngiven destination [konfigureras](er-apis-app10-0-21.md) för ett ER-format och tilldelas till den post för utskriftshantering som bearbets när ER-formatet körs. I modulen **Kundreskontra** ska du, i inställningarna för utskriftshantering, konfigurera posten **Ursprunglig** om du vill utföra följande åtgärder:

- Köra ett ER-format.
- E-posta den genererade fakturan till en kund.
- Konfigurera posten **Kopiera** så att den kör samma format.
- Skriv ut en kopia av fakturan på en nätverksskrivare.

I det här fallet måste du konfigurera olika ER-destinationer för det ER-format som körs, och du måste välja destinationer för olika utskriftshanteringsposter.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar måste funktionen **Tillåt för att konfigurera ER-destinationer per artikel förutskriftshantering** vara aktiverad i arbetsytan [Funktionshanteringen](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace). Källkoden måste också ändras för att du ska kunna konfigurera namngivna ER-destinationer i den aktuella Finance-instansen och aktivera det [nya](er-apis-app10-0-21.md) ER-API:t.

Dessutom måste ER-konfigurationen **Fritextfaktura (Excel)** [importeras](er-download-configurations-global-repo.md) till din Finance-instans.

## <a name="configure-a-new-er-destination"></a>Konfigurera en ny ER-destination

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. Välj en faktura för kundkontot **US-001**.
3. På sidan **Fritextfaktura** > fliken **Faktura** > gruppen **Utskriftshantering** väljer du **Utskriftshantering**.
4. På sidan **Inställningar för utskriftshantering** expanderar du **Modul - kundreskontra** \> **Dokument** \> **Fritextfaktura**, väljer den **ursprungliga** posten och följer sedan dessa steg:

    1.  Observera de aktuella inställningarna för den valda posten:
        -   Standardrapporten SSRS **FreeTextInvoice.Report** väljs i fältet **Rapportformat**.
        -   Namnet **\<Default\>** visas i fältet **Destination** och informerar om att det inte finns någon anpassad destination vald för tilldelad SSRS-rapport. 
    2.  I fältet **Rapportformat** väljer du ER-formatkonfigurationen **Fritextfaktura (Excel)**.
        -   Namnet på fältet **Destination** ändras till **Destinationens namn**.
        -   Namnet **\<No named destination\>** visas i fältet **Destinationsnamn** och informerar om att det inte finns någon namngiven destination vald för tilldelat ER-format.
    3.  Välj pilknappen till höger om fältet **Målnamn**.    
    4. På sidan **Namngiven destination för elektronisk rapportering**, i fältet **Namn**, anger du **Huvuddestination**.
    5. Välj **Spara**.
    6. På snabbfliken **Fildestination** [konfigurerar du](er-destination-type-email.md) destinationen för **E-post** för komponenten **Rapport**.
    7. Stäng sidan **Namngiven destination för Elektronisk rapportering**.
    8. På sidan **Konfiguration för utskriftshantering**, i fältet **Destinationsnamn** väljer du namngiven **Huvuddestination**.

    ![Konfigurera en namngiven ER-destination för det valda ER-formatet och tilldela det till en konfigurerad utskriftshanteringspost på konfigurationssidan för Utskriftshantering](./media/er-named-destinations-01.gif)

    Du har nu konfigurerat namngiven ER- destination **Huvuddestination** för formatet **Fritextfaktura (Excel)** och tilldelat den till posten **Ursprunglig** för utskriftshantering under **Modul - kundreskontra** \> **Dokument** \> **Fritextfaktura**.

5. Visa **Module - kundreskontra** \> **Konto - US-001** \> **Fritextfaktura**, välj posten **Ursprunglig** och följ sedan dessa steg:

    1. Markera och håll inne (eller högerklicka på) posten, och välj sedan **Åsidosätt**.
    2. Välj pilknappen till höger om fältet **Målnamn**.
    3. På sidan **Namngiven destination för elektronisk rapportering**, i åtgärdsfönstret, väljer du **Ny**.
    4. I fältet **Namn** anger du **US-001-destination**.
    5. På snabbfliken **Fildestination** [konfigurerar du](er-destination-type-print.md) destinationen **Skrivare** för komponenten **Rapport**.
    6. Stäng sidan **Namngiven destination för Elektronisk rapportering**.
    7. På sidan **Konfiguration för utskriftshantering**, i fältet **Destinationsnamn** väljer du namngiven destination **US-001-destination**.

    ![Konfigurera en namngiven ER-destination för det valda ER-formatet och tilldela det till en konfigurerad utskriftshanteringspost på konfigurationssidan för Utskriftshantering](./media/er-named-destinations-02.gif)

    Du har nu konfigurerat namngiven ER-destination **US-001-destination** för formatet **Fritextfaktura (Excel)** och tilldelat den till posten **Ursprunglig** för utskriftshanteringsposten under **Modul - kundreskontra** \> **Konto - US-001** \> **Fritextfaktura**.

När en fritextfaktura bearbetas körs nu ER-formatet **Fritextfaktura (Excel)** och något av följande inträffar:

- Om fritextfakturan gäller för en annan kund än US-001 skickas det genererade dokumentet med e-post.
- Om fritextfakturan gäller för kund US-001 kommer det genererade dokumentet att skrivas ut.

> [!NOTE]
> När en namngiven destination inte har definierats för en utskriftshanteringspost som bearbetas vid körning, används standarddestinationerna för ER om dess är tillgängliga för det ER-format som körs.

> [!IMPORTANT]
> På sidan **Destination för elektronisk rapportering** (**Organisationsadministration** \> **Elektronisk rapportering** \> **Elektronisk rapporteringsdestination**) kommer du, om du väljer ett ER-format som minst en namngiven destination har konfigurerats för, att meddelas om namngivna destinationers närvaro.
>
> ![Meddelande om att det finns konfigurerade namngivna destinationer för det valda ER-formatet på målsidan för elektronisk rapportering](./media/er-named-destinations-03.png)
>
> Om du tar bort standarddestinationen raderas även alla namngivna destinationer. Om dessa namngivna destinationer valts för utskriftshanteringsposter annulleras valet av dessa namngivna destinationer.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Kopiera en befintlig ER-destination som en ny namngiven destination

När standardinställningen för ER-destination är tillgänglig för ett ER-format kan den användas som mall för nya ER-destinationer. Om du vill skapa en ny ER-destination som baseras på standarddestinationen väljer du **Kopiera från standard** på **målsidan för elektronisk rapportering**. Den nya destinationen får namnet **Standard**. Du kan upprepa detta steg så många gånger som krävs.

Du kan välja vilket befintligt namn som helst som mall för en ny namngiven destination. Om du vill skapa en ny namngiven ER-destination som baseras på en vald, namngiven destination väljer du **Kopiera** på sida **Namngiven destination för elektronisk rapportering**. Den nya destinationen bär samma namn som det valda destinationen, men suffixet "Kopia" läggs till. Du kan upprepa detta steg så många gånger som krävs.

## <a name="security-considerations"></a>Säkerhetsaspekter

Du kan bara ställa in namngivna ER-destinationer på sidan **Konfiguration för utskriftshantering** om du har [behörighet](../sysadmin/role-based-security.md#permissions) att utföra den här uppgiften. Behörighet kan beviljas dig om uppdraget **Konfigurera formatdestinationen för elektronisk rapportering** [programbehörighet](../sysadmin/role-based-security.md#duties) tilldelas en av dina [säkerhetsroller](../sysadmin/role-based-security.md#security-roles). Mer information finns i [Säkerhetsbeaktanden](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)

[Ändringar av API:et för ramverket för elektronisk rapportering för Application update 10.0.17](er-apis-app10-0-17.md)

[Ändringar av API:et för ramverket för elektronisk rapportering för Application update 10.0.21](er-apis-app10-0-21.md)

[Ändra kod så att användare kan konfigurera och använda namngivna ER-destinationer](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
