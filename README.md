# HAND Plugin 

HAND é um plugin para a geração do raster Height Above Nearest Drainage (altura acima do ponto drenante mais próximo) a partir de um Modelo Digital de Elevação (MDE), bacia hidrográfica, raster de direção de fluxo e rede de drenagem.

## Descrição 

O plugin calcula o raster HAND, que representa, para cada pixel do MDE, a diferença vertical entre a sua elevação e a elevação do pixel drenante mais próximo (o pixel da rede de drenagem para o qual ele escoa). Este produto é amplamente utilizado em análises de susceptibilidade a inundações, modelagem hidrológica e mapeamento de planícies aluviais[cite: 3].

O processamento pode ser executado localmente, invocando rotinas em Python/Fortran, ou através de um backend que recebe os arquivos via HTTP e retorna o GeoTIFF resultante[cite: 4].

## Requisitos 

* QGIS 3.22+ 
* Python 3.9+ (compatível com QGIS/OSGeo4W) 
* GDAL (>=3.8) com bindings Python (osgeo.gdal) 
* NumPy 
* O separador de casas decimais deve ser o ponto (`.`) e não a vírgula (`,`).

## Uso no QGIS 

1.  Inicie o plugin através do menu `Plugins → HAND Plugin`.
2.  Selecione os arquivos de entrada (inputs):
    * Modelo Digital de Elevação - MDE (raster GeoTIFF) 
    * Bacia Hidrográfica (raster GeoTIFF) 
    * Direção de fluxo (raster GeoTIFF) 
    * Rede de drenagem (raster GeoTIFF) 
3.  Clique no botão `Gerar HAND`.

O plugin irá chamar a rotina HAND desenvolvida em Fortran. Ao finalizar, um GeoTIFF com o resultado do HAND será gerado e adicionado automaticamente ao projeto atual do QGIS.

## Licença 

MIT License   
Copyright (c) 2025 <João Vitor Lima & Adriano Paz>
