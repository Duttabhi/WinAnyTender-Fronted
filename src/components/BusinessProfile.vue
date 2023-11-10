<template>
  <!-- Main Content Section -->
  <div class="container mt-4">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card custom-card">
          <div class="card-header">
            <h5 style="font-family:cursive">Profile Form</h5>
          </div>
          <div class="card-body">
            <form id="BusinessProfileForm" @submit.prevent="submitForm">
<!--Business Category-->
              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive">Business Category</label>
                </div>
              </div>
              <!-- Drop-down with Pre-defined Values -->
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="business-category" class="col-form-label">Business Category<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <div class="form-group">
                    <select class="form-control" id="business-category" v-model="formData.businessOption" required>
                      <option value="" disabled selected>Select Business Category</option>
                      <option value="infra">Infrasturcture and Constructions</option>
                      <option value="secure">Security and Survelliance</option>
                      <option value="clean">Cleaning Services</option>
                      <option value="telcomm">Telecommunications</option>
                      <option value="change">Change Management</option>
                      <option value="manufacture">Manufacturing</option>
                      <option value="health">Healthcare</option>
                      <option value="educate">Education</option>
                    </select>
                  </div>
                </div>
              </div>  
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="company-service" class="col-form-label">Product/Services<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="company-service" v-model="formData.companyService" placeholder="E.g. Construction Management" required>
                </div>
              </div>

  <!--Company details-->
              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive">Company Background</label>
                </div>
              </div>            
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="company-name" class="col-form-label">Company Name<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="company-name" v-model="formData.companyName" placeholder="Enter your Company's Name" required>
                </div>
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="abn" class="col-form-label">Business ABN<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="abn" v-model="formData.abn" placeholder="Enter your Company's ABN" required>
                </div>
              </div>            

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="acn" class="col-form-label">Business ACN<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="acn" v-model="formData.acn" placeholder="Enter your Company's ACN" required>
                </div>
              </div>  

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="email" class="col-form-label">E-mail<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="email" v-model="formData.email" placeholder="Enter E-mail Id" required>
                </div>
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="phone" class="col-form-label">Phone<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="phone" v-model="formData.phone" placeholder="Enter Contact Info" required>
                </div>
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="estd" class="col-form-label">Year Established<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="estd" v-model="formData.estd" placeholder="Establishment year" required>
                </div>
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="addr" class="col-form-label">Business Address<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="addr" v-model="formData.addr" placeholder="Company's Address" required>
                </div>              
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="license" class="col-form-label">Business License: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="license" v-model="formData.license" placeholder="Company's License (If Applicable)">
                </div>              
              </div>

  <!--Owner Details-->
              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive">About The Owner</label>
                </div>
              </div>           
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="owner" class="col-form-label">Owner's Name<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="owner" v-model="formData.owner" placeholder="Owner's Name" required>
                </div>              
              </div>
              <!-- Multi-File Upload Option -->
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="ownerprofile" class="col-form-label">Owner's Profile/ Resume<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="file" class="form-control-file" id="ownerprofile" @change="handleOwnerDocUpload" multiple accept=".docx" required>
                </div>              
              </div>

  <!--Key Employee Details-->
              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive">About The Team/Partners</label>
                </div>
              </div>
              <div v-for="(emp, index) in employee" :key="index">
                <div class="mb-3 row">
                  <div class="col-sm-4" style="text-align: left;">
                    <button @click="removeEmployee(index)">Remove</button>
                  </div>
                </div>            
                <div class="mb-3 row">
                  <div class="col-sm-4" style="text-align: left;">
                    <label for="ename" class="col-form-label">Employee Name<a style="color:red">*</a>: </label>
                  </div>
                  <div class="col-sm-8">
                    <input type="text" class="form-control" id="ename" v-model="emp.empName" placeholder="Employee Name" required>
                  </div>              
                </div>
                <div class="mb-3 row">
                  <div class="col-sm-4" style="text-align: left;">
                    <label for="edesign" class="col-form-label">Position Title<a style="color:red">*</a>: </label>
                  </div>
                  <div class="col-sm-8">
                    <input type="text" class="form-control" id="edesign" v-model="emp.empDesignation" placeholder="Designation" required>
                  </div>              
                </div>            
                <!-- Multi-File Upload Option -->
                <div class="mb-3 row">
                  <div class="col-sm-4" style="text-align: left;">
                    <label for="eprofile" class="col-form-label">Employee Profile/ Resume<a style="color:red">*</a>: </label>
                  </div>
                  <div class="col-sm-8">
                    <input type="file" class="form-control-file" id="eprofile" @change="handleEmpFileUpload($event, index)" accept=".docx" required>
                  </div>              
                </div>
              </div>            
                <div class="mb-3 row">
                  <div class="col-sm-4" style="text-align: left;">
                    <button @click="addEmployee">Add Person</button>
                  </div>
                </div>

  <!--Additional Work-->
              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive">Business Experience</label>
                </div>
              </div>             
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="workPic" class="col-form-label">Attach Pictures: </label>
                </div>
                <div class="col-sm-8">
                  <input type="file" class="form-control-file" id="workPic" @change="handleImageUpload" multiple accept=".jpg">
                </div>              
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="prevWork" class="col-form-label">Previous Work<a style="color:red">*</a>: </label>
                </div>
                <div class="col-sm-8">
                  <input type="file" class="form-control-file" id="prevWork" @change="handleDocUpload" multiple accept=".docx" required>
                </div>              
              </div>
              
              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="awards" class="col-form-label">Awards/Achievements: </label>
                </div>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="awards" v-model="formData.awards" placeholder="Enter Comma Separated Values">
                </div>  
              </div>

              <div class="mb-3 row">
                <div class="col-sm-4" style="text-align: left;">
                  <label for="addInfo" class="col-form-label">Additional Info:</label>
                </div>
                <div class="col-sm-8">
                  <textarea class="form-control" id="addInfo" v-model="formData.additionalData" rows="3" placeholder="Type your message here"></textarea>
                </div>              
              </div>

              <div class="mb-3 row">
                <div class="col-sm-12" style="text-align:center;background-color:#f0f0f0;font-weight:bold;">
                  <label style="font-family:cursive"><a style="font-style:bold">Remark: </a><a style="color:red">*</a> marked fields are required</label>
                </div>
              </div>   

              <button type="submit" class="btn btn-primary">Submit</button>
            </form>
            <iframe v-if="loading" src="https://giphy.com/embed/gJ3mEToTDJn3LT6kCT" width="64" height="64" frameBorder="0" allowFullScreen></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'BusinessProfile',
  props: {
    msg: String
  },
  data() {
    return {
      formData: {
        businessOption: '',
        companyName: '',
        abn: '',
        acn: '',
        estd: '',
        addr: '',
        license: '',
        owner: '',
        addInfo: '',
        awards: '',
        phone: '',
        email: '',
        companyService: '',
      },
      ownerDocs: [],
      workPic: [],
      prevWork: [],
      loading: false,
      employee: [{ empName: '', empDesignation: '', empCv: null }]
    };
  },
  methods: {
    handleOwnerDocUpload(event){
      this.ownerDocs = Array.from(event.target.files);
    },
    handleEmpFileUpload(event, index){
      this.employee[index].empCv = event.target.files[0];
    },
    handleImageUpload(event) {
      this.workPic = Array.from(event.target.files);
    },
    handleDocUpload(event){
      this.prevWork = Array.from(event.target.files);
    },
    addEmployee(){
      this.employee.push({ empName: '', empDesignation: '', empCv: null });
    },
    removeEmployee(index) {
      this.employee.splice(index, 1);
    },
    async submitForm() {
      this.loading = true;
      console.log('Processing Started for... ' + this.companyName)
      const postData = new FormData();
      postData.append('businessOption', this.formData.businessOption);
      postData.append('companyName', this.formData.companyName);
      postData.append('abn', this.formData.abn);
      postData.append('acn', this.formData.acn);
      postData.append('estd', this.formData.estd);
      postData.append('addr', this.formData.addr);
      postData.append('license', this.formData.license);
      postData.append('owner', this.formData.owner);
      postData.append('additionalData', this.formData.addInfo);
      postData.append('awards', this.formData.awards);
      postData.append('phone', this.formData.phone);
      postData.append('email', this.formData.email);
      postData.append('companyService', this.formData.companyService);
      postData.append('numEmployees', this.employee.length);
      for (let i = 0; i < this.ownerDocs.length; i++) {
        postData.append('ownerDocs', this.ownerDocs[i]);
      }
      for (let i = 0; i < this.workPic.length; i++) {
        postData.append('workPic', this.workPic[i]);
      }
      for (let i = 0; i < this.prevWork.length; i++) {
        postData.append('prevWork', this.prevWork[i]);
      }
      this.employee.forEach((emp, index) => {
        postData.append(`emp[${index}][eName]`, emp.empName);
        postData.append(`emp[${index}][eDesignation]`, emp.empDesignation);
        postData.append(`emp[${index}][eCv]`, emp.empCv);
      });
      try {
        const response = await axios.post('http://127.0.0.1:5000/process_data', postData, {
          headers: {
            "Content-Type": "multipart/form-data",
          },
          responseType: 'blob',
        });
		
        this.loading = false;
		
        // Process the response (e.g., handle the downloaded docx file)
        console.log("Processing Ended...")
        
        const dataSizeInBytes = response.data.length;
        console.log(`Response data size: ${dataSizeInBytes} bytes`)
        
        // Create a Blob from the response data
        const blob = new Blob([response.data], { type: 'application/vnd.openxmlformats-officedocument.wordprocessingml.document' });

        // Create a link element to download the Blob as a file
        const link = document.createElement('a');
        link.href = window.URL.createObjectURL(blob);
        link.setAttribute('download', 'document.docx');
        document.body.appendChild(link);  
        link.click();        
        
      } catch (error) {
        console.error('Error... ', error);
        this.loading = false;
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* Custom CSS for the card shadow */
.custom-card {
  box-shadow: 0 16px 32px rgba(0, 0, 0, 0.1);
}
/* Optional styling for the card header and body */
.card-header {
  background-color: #f0f0f0;
  font-weight: bold;
}
.card-body {
  padding: 20px;
}
</style>
