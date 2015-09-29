============
OWFpdfBundle 
============

.. image:: https://github.com/Open-Wide/OWPublishAgendaBundle/raw/master/doc/images/Open-Wide_logo.png

:Extension: OW Fpdf Bundle v1.0
:Requires: Symfony 2
:Author: Open Wide http://www.openwide.fr

Presentation
============

[FPDF] http://fpdf.org/

This bundle provides a complete system to create and display PDF. 

Other features include user's choice of unit of measure, page format and margins; header and footer management; automatic page and line breaks and text justification; JPEG and PNG image support; and TrueType, Type1 and encoding support.


Installation
============

1. Add ``FpdfBundle`` in your project

    * Via composer (TODO packagist)
    
        Add the bundle in your ``composer.json``
        
        .. code-block:: json
        
            {
              "require": {
                "open-wide/fpdf-bundle": "dev-master"
              }
            }


    * Via a submodule
    
        .. code-block:: bash
        
            mkdir -p src/OpenWide
            git submodule add https://github.com/Open-Wide/OwFpdfBundle.git src/OpenWide/FpdfBundle



2. Enable the Bundle in your ``EzPublishKernel.php`` file:

    .. code-block:: php
    
        <?php
        // ezpublish/EzPublishKernel.php
    
        public function registerBundles()
        {
          $bundles = array(
            // ...
            new OpenWide\FpdfBundle\OpenWideFpdfBundle(),
          );
        }


Usage
=====

$pdf = $this->container->get('ow_fpdf.fpdf');


Example
=======

$pdf = $this->container->get('ow_fpdf.fpdf');

$pdf->AddPage();

$pdf->SetFont('Arial','B',16);

$pdf->Cell(40,10,'Hello World !');

$pdf->Output();


Other
=====

FPDF documentation: http://fpdf.org/
