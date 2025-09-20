HAND Plugin

HAND — plugin para geração do raster Height Above Nearest Drainage (altura acima do ponto drenante mais próximo) a partir de: 
Modelo Digital de Elevação (MDE), 
bacia hidrográfica, 
raster de direção de fluxo e rede de drenagem.

Descrição

O plugin calcula o raster HAND que representa, para cada pixel do DEM, a diferença vertical entre a elevação do pixel e a elevação do pixel drenante mais próximo (o pixel da rede de drenagem para o qual ele escoa). 
O produto é amplamente utilizado em análises de susceptibilidade a inundações, modelagem hidrológica e mapeamento de planícies aluviais.
O processamento pode ser executado localmente (invocando rotinas Python/Fortran) ou por meio de um backend que receba arquivos via HTTP e retorne o GeoTIFF resultante.

Requisitos

QGIS 3.22+.
Python 3.9+ (compatível com  QGIS/OSGeo4W).
GDAL(>=3.8) com bindings Python (osgeo.gdal).
NumPy.
Separador de casas decimais deve ser o ponto (.) não vírgula.

Uso no QGIS

Inicie o plugin pelo menu Plugins → HAND Plugin.

Selecione os inputs:
-Modelo Digital de Eleveção - MDE (raster GeoTIFF)
-Bacia Hidrográfica (raster GeoTIFF)
-Direção de fluxo (raster GeoTIFF)
-Rede de drenagem (raster GeoTIFF)

Clique em no botão Gerar HAND. O plugin fará:
Chamar a rotina HAND desenvolvida em Fortran.

Ao finalizar, será gerado um GeoTIFF com o HAND que será adicionado automaticamente ao projeto atual do QGIS.

MIT License
Copyright (c) 2025 <João Vitor Lima & Adriano Paz>