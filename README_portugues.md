# HAND Plugin

O **HAND** é um plugin para geração do raster de **Height Above Nearest Drainage (HAND)** — altura em relação ao ponto de drenagem mais próximo — a partir de um **Modelo Digital de Elevação (MDE)**, **bacia hidrográfica**, **raster de direção de fluxo** e **rede de drenagem**. Além disso, gera um **mapa de áreas propensas à inundação** com base em um limiar definido pelo usuário.

---

## Descrição

O plugin calcula o raster HAND, que representa, para cada pixel do MDE, a **diferença vertical** entre sua elevação e a elevação do pixel de drenagem mais próximo (o pixel da rede de drenagem para o qual ele escoa).

Esse produto é amplamente utilizado em **análise de suscetibilidade a inundações**, **modelagem hidrológica** e **mapeamento de planícies de inundação**.

Além disso, o plugin gera um **mapa de áreas propensas à inundação**, classificando como suscetíveis as áreas cujos valores de HAND estão abaixo do limiar especificado.

O processamento pode ser executado **localmente**, por meio de **rotinas em Python/Fortran**, ou via um **backend**, que recebe os arquivos de entrada via HTTP e retorna o GeoTIFF resultante.

---

## Requisitos

- QGIS 3.22+  
- Python 3.9+ (compatível com QGIS/OSGeo4W)  
- GDAL (≥ 3.8) com bindings Python (`osgeo.gdal`)  
- NumPy  
- O separador decimal deve ser ponto (`.`), e não vírgula (`,`)

---

## Uso no QGIS

1. Inicie o plugin pelo menu: `Plugins → HAND Plugin`.  
2. Selecione os arquivos de entrada:
   - **Modelo Digital de Elevação (MDE)** — raster GeoTIFF (Tipo de dado: Float)  
   - **Bacia hidrográfica** — raster GeoTIFF (Tipo de dado: Inteiro)  
   - **Direção de fluxo** — raster GeoTIFF (Tipo de dado: Inteiro)  
   - **Rede de drenagem** — raster GeoTIFF (Tipo de dado: Inteiro)  
3. Defina os caminhos de saída para o raster HAND e o mapa de áreas propensas à inundação, e informe o limiar de inundação (em metros).  
4. Clique no botão **"Gerar HAND"**.

O plugin irá chamar a rotina HAND desenvolvida em **Fortran**.  

Ao final do processamento, dois arquivos **GeoTIFF** serão gerados e automaticamente adicionados ao projeto atual do QGIS:

- O resultado HAND (raster GeoTIFF, Tipo de dado: Float)  
- O mapa de áreas propensas à inundação (raster GeoTIFF, Tipo de dado: Byte), onde as áreas abaixo do limiar são classificadas como suscetíveis à inundação  

---

## Licença

**Licença MIT**  
Copyright (c) 2025 João Vitor Lima & Adriano Paz