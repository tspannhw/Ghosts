````

   SELECT SNOWFLAKE.CORTEX.COMPLETE('pixtral-large', 
'Please fully describe this image and let me know if this is a ghost.  Respond in compact JSON format.',
TO_FILE('@GHOST_IMAGES_STAGE',
'2022-11-13_16-01-06_269.jpeg')) AS SpectralDescription;


{
  "description": "The image shows a piece of flatbread or pizza with a face-like appearance created by toppings. The bread has a light brown crust with some darker spots. There are two black olives positioned to resemble eyes and a red sauce arranged to look like a mouth, giving it a ghost-like or face-like appearance. The bread is placed on a wire rack lined with aluminum foil, which is set on a baking sheet.",
  "is_ghost": "The bread is decorated to resemble a ghost or face using olives and sauce."
}

SELECT AI_CLASSIFY(TO_FILE('@GHOST_IMAGES_STAGE', 'Image_fx (16).jpg'),
    ['Spectral Entities', 'Non-Human Entities', 'Cat', 'Costumed Human', 'Residual Imprints']) AS room_classification;

{
  "labels": [
    "Costumed Human"
  ]
}


````
