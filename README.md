# Feed_forward_Cifar-100

# Proyecto de aprendizaje Cifar-100

En este proyecto desarrollaremos un clasificador de imágenes basado en Deep Learning utilizando el conjunto de datos CIFAR-100. La solución combina procesamiento de imágenes, redes neuronales profundas (MLP) y una interfaz web interactiva mediante Gradio para facilitar la visualización y uso del modelo.

# ¿Que es cifar-100?

CIFAR-100 es un conjunto de datos ampliamente utilizado en el campo del Deep Learning. Contiene 60,000 imágenes (50,000 entrenamiento - 10,000 prueba) a color de tamaño 32x32 píxeles, distribuidas en 100 clases diferentes, con 600 imágenes por clase (500 de entrenamiento - 100 de prueba). Estas clases incluyen objetos variados como animales, vehículos, árboles, frutas, instrumentos, etc.

# ¿Qué haremos técnicamente?

**1. Carga y Preprocesamiento de Datos**  
   - Cargaremos el conjunto de datos CIFAR-100.
   - Redimensionaremos y normalizaremos las imágenes.
   - Convertiremos las etiquetas a formato categórico (one-hot encoding).
   - Aplanaremos las imágenes para pasarlas a una red totalmente conectada (MLP).

**2. Construcción del Modelo**  
   - Diseñaremos una red neuronal MLP (Multilayer Perceptron).
   - Usaremos capas densas con funciones de activación ReLU.
   - Añadiremos Dropout y regularización L2.
   - Finalizaremos con una capa `softmax` para clasificar entre 100 clases.

**3. Entrenamiento del Modelo**  
   - Compilaremos el modelo con optimizador SGD (con Nesterov), pérdida `categorical_crossentropy` y métrica `accuracy`.
   - Usaremos callbacks como `EarlyStopping`, `ModelCheckpoint`, `Learning rate scheduler` y `TensorBoard`.
   - Entrenaremos con validación y ajustaremos el learning rate dinámicamente.

**4. Evaluación y Métricas**  
   - Analizaremos el rendimiento del modelo con:
   - Matriz de confusión
   - Curvas de precisión y recall
   - Curvas ROC/AUC
   - Histogramas de desempeño por clase
   - Identificaremos las clases con mejor y peor desempeño.

**5. Interfaz Interactiva con Gradio**  
   - Implementaremos una interfaz web sencilla con Gradio.
   - Permitiremos al usuario cargar imágenes desde su dispositivo.
   - El modelo devolverá la clase predicha como salida textual.

# Requisitos previos
   - Google Colab: Acceso a una cuenta de Google y Google Colab.
   
   - Python 3.x: Si deseas ejecutar el proyecto localmente.
   
   - Internet: Para descargar el conjunto de datos de CIFAR-100 y los modelos.

# Instrucciones de uso 

   **Uso en Google Colab (Drive)**
   - **Accede a Google Colab:**

     -Abre Google Colab en tu navegador: https://colab.research.google.com.

   - **Carga el proyecto en Google Drive:**

     -Si no lo has hecho ya, sube tu repositorio a Google Drive.

     -Asegúrate de tener el repositorio guardado en una carpeta en Google Drive para poder accederlo fácilmente.

   - **Cargar el archivo de CIFAR-100:**

     -El primer notebook requiere que descargues el archivo de CIFAR-100.

     -Después de descargarlo, sube el archivo comprimido a tu Google Drive.

     -En el notebook, cambia las rutas de acceso al archivo para que apunten a la carpeta de Google Drive donde guardaste el archivo CIFAR-100.

   - **Ejecutar el Notebook:**

     -En el notebook de Google Colab, ejecuta todas las celdas para cargar los datos, preprocesarlos, construir y entrenar el modelo.

     -Si todo está configurado correctamente, el modelo se entrenará y podrás visualizar los resultados de la clasificación.

   - **Guardar los resultados:**

     -Puedes guardar el modelo entrenado en Google Drive, o también puedes descargarlo para usarlo en un entorno local si lo prefieres.

   **Uso en google colab (entorno local)**

   - **Descargar el archivo de CIFAR-100:**

      -Descarga el archivo de CIFAR-100 desde este enlace.

      -Una vez descargado, sube el archivo a tu entorno de Google Colab.

   - **Cargar los datos localmente:**

      -Cambia las rutas de acceso en el notebook de Colab para que apunten a la ubicación donde subiste el archivo en Colab.

     -Asegúrate de descomprimir el archivo antes de cargar los datos.

   - **Ejecutar el notebook:**

     -Ejecuta las celdas en orden dentro de Google Colab. Esto cargará los datos, los preprocesará y entrenará el modelo.

   **Uso del Modelo Preentrenado**
     
   - **Descargar el Modelo:**

     -Si prefieres utilizar un modelo preentrenado, puedes descargarlo desde el repositorio del proyecto o desde algún enlace proporcionado en la documentación.

     -Asegúrate de que la ruta del modelo esté correctamente configurada en el código.

   - **Cambiar las Rutas:**

     -Asegúrate de cambiar las rutas a las de tu archivo local o en Google Drive.

     -La ruta debe ser actualizada dentro de los notebooks para que apunten a la ubicación donde descargaste el modelo.

   - **Cargar el Modelo:**

     -Una vez configurada la ruta, ejecuta el código para cargar el modelo preentrenado y realizar la validación en los datos de CIFAR-100.

# Ventajas de usar gradio

- Fácil de compartir: El enlace público permite compartir con cualquier persona.
- Feedback visual: Muestra las probabilidades de las principales predicciones.
- Interfaz amigable: Permite a las personas interactuar con el modelo sin la necesidad de escribir código.

# Conclusión

**1. Rendimiento General:**

   ❌ El modelo MLP no logró un buen rendimiento para CIFAR-100.

**2. Limitaciones:**
   - Las MLPs procesan imágenes aplanadas, perdiendo la información espacial.
   - Para imágenes, las redes convolucionales (CNN) suelen tener mejor rendimiento.
   - El modelo puede tener dificultades con objetos rotados o en diferentes posiciones.
   -El modelo tiene overfitting.

**3. Mejoras Potenciales:**
   - Probar arquitecturas más complejas (más capas, más unidades).
   - Implementar técnicas de aumentación de datos (rotaciones, volteos, zoom).
   - Ajustar los hiperparámetros mediante búsqueda de cuadrícula o aleatoria.
   - Migrar a una arquitectura CNN para mejorar significativamente el rendimiento.

**4. Comparación con otro tipo de arquitecturas:**
   - Convolucionales


# Documentación y enlaces útiles
- [Repositorio de Cifar-100](https://www.cs.toronto.edu/~kriz/cifar.html)
  
- [Documentación de Keras](https://keras.io/api/optimizers/)
