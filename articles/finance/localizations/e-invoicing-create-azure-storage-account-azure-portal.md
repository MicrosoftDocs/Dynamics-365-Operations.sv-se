---
title: Skapa ett Azure-lagringskonto i Azure-portalen
description: I denna artikel beskrivs hur du skapar ett Azure-lagringskonto för e-fakturering.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5eca23985c48f4e577bd4567cc2e324df5aa9690
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291649"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Skapa ett Azure-lagringskonto i Azure-portalen

[!include [banner](../includes/banner.md)]

Alla elektroniska filer som genereras av e-faktureringstjänsten eller går till tjänsten under bearbetningen lagras i dina Microsoft Azure-lagringskontobehållare. Om du vill säkerställa att e-fakturering har åtkomst till dessa behållare måste du ange token för signatur för delad åtkomst (SAS) för lagringskontot för e-faktureringstjänsten. För att säkerställa att token lagras på ett säkert sätt bör du dessutom inte ange SAS-token direkt. Lagra den istället i ett Azure-nyckelval, och tillhandahåll en hemlighet för Azure Key Vault.

1. Öppna det lagringskonto som du vill använda med tjänsten för e-fakturering.
2. Gå till **Inställningar** \> **Konfiguration** och se till att parametern **Tillåt offentlig åtkomst för Blob** är inställd på **Aktivera**.
3. Gå till **Datalagring** \> **Behållare** och skapa en behållare.
4. Ange ett namn på behållaren och ställ in fältet **Offentlig åtkomstnivå** på **Privat (ingen anonym åtkomst)**.
5. Öppna den nya behållaren och gå till **Inställningar** \> **Åtkomstpolicy**.
6. Välj **Lägg till policy** om du vill lägga till en lagrad åtkomstpolicy.
7. Ange fältet **Identifierare** efter behov.
8. I fältet **Behörigheter** väljer du samtliga behörigheter.

    ![Alla behörigheter som har markerats i fältet Behörigheter i dialogrutan Lägg till policy.](media/e-invoicing-azure-1.png)

9. Ange start- och slutdatum. Slutdatumet måste vara i framtiden.
10. Klicka på **OK** om du vill spara policy och spara sedan ändringarna i behållaren.
11. Gå till **Inställningar** \> **Tokens för delad åtkomst** och ange fältvärdena.
12. Ange start- och slutdatum. Slutdatumet måste vara i framtiden.
13. I fältet **Behörigheter** väljer du samtliga följande behörigheter:

    - Läsa
    - Lägg till
    - Skapa
    - Skriv
    - Delete
    - Lista

14. Välj **Generera SAS-token och URL**.
15. Kopiera och lagra värdet i fältet **Blob SAS URL**. Detta värde används senare i denna procedur och kallas då för *URI för signatur för delad åtkomst*.
16. Öppna det nyckelvalv som du vill använda med e-fakturering.
17. Gå till **Inställningar** \> **Hemligheter** och välj sedan **Generera/importera** om du vill skapa en hemlighet.
18. På sidan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
19. Ange namnet på hemligheten. Detta namn används under installationen av tjänsten i RCS (Regulatory Configuration Service) och kommer att kallas *hemligt namn för nyckelvalv*. Mer information om hur du konfigurerar RCS finns i [Konfigurerar Regulatory Configuration Services (RCS)](e-invoicing-set-up-rcs.md).
20. I fältet **Värde** anger du den URI för signatur för delad åtkomst som du tidigare kopierade.
21. Markera **Skapa**.
