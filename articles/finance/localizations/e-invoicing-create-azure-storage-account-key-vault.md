---
title: Skapa ett Azure Storage-konto och ett nyckelvalv
description: I det här avsnittet beskrivs hur du skapar ett Azure Storage-konto och nyckelvalv.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 5a883011bbff6d82504497d739c07f1ada9e5f69
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2020
ms.locfileid: "4448185"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Skapa ett Azure Storage-konto och ett nyckelvalv

[!include [banner](../includes/banner.md)]



Tilläggstjänsten elektronisk fakturering tar ansvar för lagringen av alla dina affärsdata i de Microsoft Azure-resurser som företaget äger. Du måste skapa två huvudresurser för Azure om du vill säkerställa att tjänsten fungerar korrekt och att alla affärsdata som behövs för och genereras av tilläggstjänsten elektronisk fakturering endast används av tillägget.

- Ett Azure Storage-konto (Blob Storage) för att lagra elektroniska fakturor
- Ett Azure Key-valv för lagring av certifikat och Uniform Resource Identifier (URI) för lagringskontot

> [!NOTE]
> En särskild nyckelvalvresurs och kundens Blob Storage måste allokeras specifikt för att användas med tillägget för elektronisk fakturering.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra stegen i det här ämnet måste du se till att följande uppgifter har slutförts:

- Skapa en nyckelvalvresurs i Azure. Mer information om mått finns i [Om Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Skapa ett Azure Storage-konto (Blob Storage). Mer information finns i [Underhålla Azure Storage-kontot](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Översikt

I det här avsnittet ska du utföra två huvudsteg:

- Konfigurera Azure Storage-kontot för att hämta lagringskontots URI.
- Ställ in nyckelvalvet för att lagra lagringskontots URI.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Konfigurera Azure Storage-kontot för att hämta lagringskontots URI

1. Öppna det lagringskonto som du vill använda med tillägget elektroniska fakturering.
2. Gå till **Blob Service** \> **Behållare** och skapa en ny behållare.
3. Ange ett namn på behållaren och ställ in fältet **Offentlig åtkomstnivå** på **Privat (ingen anonym åtkomst)**.
4. Öppna behållaren och gå till **Inställningar \> Åtkomstpolicy**.
5. Välj **Lägg till policy** om du vill lägga till en lagrad åtkomstpolicy.
6. Ange fältet **Identifierare** och **Behörigheter** efter behov. I fältet **Behörigheter** bör du välja alla behörigheter.

    ![Bevilja behörighet för Blob Storage](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Ange start- och utgångsdatum. Utgångsdatumet måste vara i framtiden.
8. Klicka på **OK** om du vill spara policy och spara sedan ändringarna i behållaren.
9. Gå tillbaka till lagringskontot och öppna **Lagringsutforskaren (förhandsversion)**.
10. Högerklicka på behållaren och välj sedan **Hämta signatur för delad åtkomst**.
11. I dialogrutan **Signatur för delad åtkomst** kopiera och spara värdet **URI**. Det här värdet används i nästa procedur och kallas för *Signatur för delad åtkomst URI*.

    ![Markera och kopiera URI-värdet](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Ställ in nyckelvalvet för att lagra lagringskontots URI

1. Öppna det nyckelvalv som du vill använda med tillägget elektroniska fakturering.
2. Gå till **Inställning** \> **Hemligheter** och välj sedan **Generera/importera** om du vill skapa en ny hemlighet.
3. På sidan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
4. Ange namnet på hemligheten. Det här namnet används under installationen av tjänsten i RCS (Regulatory Configuration Service) och kommer att kallas *nyckelvalvets hemliga namn*.
5. I fältet **Värde** markera **Signatur för delad åtkomst URI** och välj sedan **Skapa**.
6. Ställ in åtkomstprincipen så att tillägget elektronisk fakturering på den korrekta nivån för säker åtkomst till den hemlighet som du har skapat. Gå till **Inställningar \> Åtkomstprinciper** och välj **Lägg till åtkomstprincip**.
7. Ange de hemliga behörigheterna för åtgärderna **Hämta** och **Lista**.

    ![Bevilja tjänståtkomst](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Ange certifikatbehörigheter för åtgärderna **Hämta** och **Lista**.

    ![Bevilja certifikatbehörighet](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. I dialogrutan **Primär** välj primär genom att lägga till **tillägget elektronisk fakturering**.
10. Välj **Lägg till** och välj sedan **Spara ändringar i nyckelvalv**.
11. På sidan **Översikt** kopiera värdet **DNS-namn** för nyckelvalvet. Det här värdet kommer att användas under installationen av tjänsten i RCS och kallas *nyckelvalv-URI*.
