# Utilizar la imagen base de Ubuntu 20.04
FROM ubuntu:20.04

# Evitar que se muestre un mensaje interactivo al instalar paquetes
ENV DEBIAN_FRONTEND=noninteractive

# Actualizar y descargar las dependencias necesarias
RUN apt-get update && \
  apt-get install -y curl software-properties-common && \
  curl -sL https://deb.nodesource.com/setup_14.x | bash - && \
  apt-get install -y nodejs && \
  apt-get install -y nano && \
  npm install -g json-server@0.17.4

# Establecer el directorio de trabajo en /app
WORKDIR /app

# Crear el archivo db.json con el contenido dado
RUN echo '{ \
  "influx": { \
  "target": [ \
  { "value": "uid63e889b9f4664cd68fee2e", "label": "Cell", "code": "cell" }, \
  { "value": "uid33a18561cf114a43ad85ae", "label": "Machine", "code": "machine" } \
  ], \
  "indicator": { \
  "uid3aa99681ecda44c791f86e": [ \
  { "value": "uid803f25d32f5f4a55820234", "label": "Actual production time", "code": "apt" }, \
  { "value": "uid9a6d9af088c24ba0892b9d", "label": "Actual unit busy time", "code": "aubt" }, \
  { "value": "uide3694979df1f4eb7bb856c", "label": "Actual order execution time", "code": "aoet" }, \
  { "value": "uid83c9c9608599454991d3f7", "label": "Planned busy time", "code": "pbt" }, \
  { "value": "uid895f0872b92343f0814a22", "label": "Corrective maintenance time", "code": "cmt" }, \
  { "value": "uid5e73fdec3c284a1e9d74fd", "label": "Preventive maintenance time", "code": "pmt" }, \
  { "value": "uidec888444673647b6ab647c", "label": "Good Quantity", "code": "gq" }, \
  { "value": "uidbe5026b94e8b49418c9c6a", "label": "Scrap Quantity", "code": "sq" }, \
  { "value": "uid841ae7bc80124e6abcd330", "label": "Rework Quantity", "code": "rq" }, \
  { "value": "uid12f78520d3d64551a1653b", "label": "Planned Run Time Per Unit", "code": "prt" } \
  ], \
  "uidf2b3376a25c2403aac5b8d": [ \
  { "value": "uid8a0741a126d14f2f81583e", "label": "Process Field", "code": "process_field" } \
  ] \
  }, \
  "kpi": [ \
  { "value": "uiddf3333c232dd4077a1a232", "label": "Oee", "code": "oee" }, \
  { "value": "uid7e06aaf9ff644d05b43ef7", "label": "Availability", "code": "availability" }, \
  { "value": "uid325dd00b857c4cfbbfaf8b", "label": "Effectiveness", "code": "effectiveness" }, \
  { "value": "uid8e4e7796348b4ee195be2e", "label": "Quality Ratio", "code": "quality_ratio" }, \
  { "value": "uidbaff8d9c5d694a85a8c53b", "label": "Scrap Ratio", "code": "scrap_ratio" }, \
  { "value": "uide3455db2d45146ceb0fa63", "label": "Rework Ratio", "code": "rework_ratio" }, \
  { "value": "uid0130c4de6a934059a54890", "label": "Corrective Maintenance Ratio", "code": "corrective_maintenance_ratio" }, \
  { "value": "uid56ac00325808497e86d237", "label": "Production Process Ratio", "code": "production_process_ratio" }, \
  { "value": "uida30c6f03a3fb4aa7be9a35", "label": "Utilization Efficiency", "code": "utilization_efficiency" } \
  ], \
  "asset": { \
  "uid33a18561cf114a43ad85ae": [ \
  { "value": "uidb62abd71820045be887c8a", "label": "taladro", "code": "taladro" }, \
  { "value": "uidc3209d1d7da34938a1466c", "label": "fresadora", "code": "fresadora" }, \
  { "value": "uide92c2d8ff1ab4a2498df56", "label": "troqueladora", "code": "troqueladora" } \
  ], \
  "uid63e889b9f4664cd68fee2e": [ \
  { "value": "uide0692ab8a864465bbd9e7a", "label": "Unique Cell", "code": "unique_cell" }, \
  { "value": "uide0692ab8a864465bbd9e7b", "label": "Second Cell", "code": "second_cell" } \
  ] \
  }, \
  "timeframe": [ \
  { "value": "uid9f3dd4912b2b4c57996d9d", "label": "Nothing", "code": "nothing" }, \
  { "value": "uidaff07382a4484c58911dff", "label": "Seconds", "code": "seconds" }, \
  { "value": "uide9404a519960469ca374ec", "label": "Minutes", "code": "minutes" }, \
  { "value": "uid04ec068c151444aab0fc50", "label": "Hours", "code": "hours" }, \
  { "value": "uidfe76c3d32c904bf58a0914", "label": "Days", "code": "days" }, \
  { "value": "uid927eae36c03542a2af8a5b", "label": "Weeks", "code": "weeks" }, \
  { "value": "uidd789d8e8670e43208d8077", "label": "Months", "code": "months" }, \
  { "value": "uidb37df2413bd049c28a5940", "label": "Quarters", "code": "quarters" }, \
  { "value": "uid9efa76af00a645648a4e9b", "label": "Years", "code": "years" } \
  ], \
  "aggregated": [ \
  { "value": "uid764f7ca2f29d424fa04eaa", "label": "Accumulated", "code": "accumulated" }, \
  { "value": "uid6c707423095a432193f41e", "label": "Average", "code": "average" }, \
  { "value": "uid383a4dab719247c089f863", "label": "Maximum", "code": "maximum" }, \
  { "value": "uide2972aaad0204b1c98a521", "label": "Minimum", "code": "minimum" } \
  ], \
  "production": [ \
  { "value": "uid3aa99681ecda44c791f86e", "label": "Production", "code": "production" }, \
  { "value": "uidf2b3376a25c2403aac5b8d", "label": "Process", "code": "process" } \
  ], \
  "relaciones": [ \
  { "cell": "uide0692ab8a864465bbd9e7a", "machines": ["taladro"] }, \
  { "cell": "uide0692ab8a864465bbd9e7b", "machines": ["fresadora", "troqueladora"] } \
  ] \
  } \
  }' > /app/db.json

# Establecer el punto de entrada para el contenedor
ENTRYPOINT ["sh", "-c", "json-server --watch db.json --host 0.0.0.0 -p 8000"]
