<template>
  <div>
    <button class="btn btn-success" @click="downloadPdf">Download Pdf</button>
  </div>
</template>

<script>
export default {
  name: "DownloadPdfButton",
  props: {
    pdfUrl: {
      type: String,
      required: true,
    },
    pdfFileName: {
      type: String,
      required: true,
    },
    pdfUrl2: {
      type: String,
      required: true,
    },
    pdfFileName2: {
      type: String,
      required: true,
    },
    pdfUrl3: {
      type: String,
      required: true,
    },
    pdfFileName3: {
      type: String,
      required: true,
    },
    pdfUrl4: {
      type: String,
      required: true,
    },
    pdfFileName4: {
      type: String,
      required: true,
    },
    pdfFileName5: {
      type: String,
      required: true,
    },
  },
  methods: {
    downloadPdf() {
      // create element <a> for download PDF
      const link = document.createElement("a");
      link.href = this.pdfUrl;
      link.target = "_blank";
      link.download = this.pdfFileName;
      console.log("pdfFileName", this.pdfFileName);

      // Simulate a click on the element <a>
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    },
  },
};
</script>
