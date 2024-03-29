---
title: Konfigurera Azure-resurser för e-fakturering
description: Det här ämnet ger en översikt över processen för att ställa in Microsoft Azure-resurser för e-fakturering.
author: gionoder
ms.date: 01/26/2022
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
ms.openlocfilehash: f11e4eac831d54a6cac765a5adc4e4ffddbe0a22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283098"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Konfigurera Azure-resurser för e-fakturering

[!include [banner](../includes/banner.md)]

Processen för inställning av Microsoft Azure-resurser för e-fakturering har tre steg. De första två stegen, "Skapa ett nyckellager för Azure i Azure-portal" och "Skapa ett lagringskonto för Azure i Azure-portal", är obligatoriska. Det tredje steget, "Konfigurera en SharePoint-anslutning", är valfritt.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Skapa ett Azure-nyckelvalv i Azure-portalen

Skapa ett nyckelvalv i din Azure-prenumeration. Vi rekommenderar att du skapar ett separat nyckelvalv för e-fakturering och att du inte kombinerar hemligheter tillsammans med andra program. Skapa så många hemligheter och certifikat som du behöver för dina scenarier i elektroniska dokument. Du måste skapa minst en hemlighet för att spara token för signatur för delat åtkomst (SAS) för det Azure-lagringskonto som du ska skapa i nästa steg.

Information om hur du utför det här steget finns i [Sakap ett Azure-nyckelvalv i Azure-portalen](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Skapa ett Azure-lagringskonto i Azure-portalen

Du äger alla elektroniska dokument och filer som genereras av e-faktureringstjänsten eller öppnar tjänsten. Dessa dokument och filer lagras på ett Azure-lagringskonto som du skapar i ditt Azure-abonnemang. Tjänsten kommer åt ditt lagringskonto med hjälp av den SAS-token som tas från din Key Vault-hemlighet.

Information om hur du utför det här steget finns i [Skapa ett Azure-lagringskonto i Azure-portalen](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Konfigurera en SharePoint-anslutning

I vissa situationer kanske du måste spara elektroniska filer och SharePoint hämta dem från SharePoint. Om du vill vara säker på att e-faktureringstjänsten har åtkomst till dina SharePoint-mappar konfigurerar du åtkomst till SharePoint.

Information om hur du utför det här steget finns i [Konfigurera en SharePoint-anslutning](e-invoicing-create-sharepoint-connection.md).
