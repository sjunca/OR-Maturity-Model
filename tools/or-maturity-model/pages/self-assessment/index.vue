<template>
    <div class="or-maturity-wrap">
        <div class="or-maturity-title">
            <div class="holder">
                <div class="svg-bg">
                    <img src="~/assets/Op-Risk.svg">
                </div>
                <div class="text-content">
                    <h1>Operational Risk Management</h1>
                    <h2>Maturity Model Self-Assessment Tool</h2>
                    <p>Sphera helps businesses improve decision-making and performance with an integrated view of their unique risk portfolio.</p>
                    <!--<p style="margin-top: 15px;font-weight: normal;">Answer each question according to your business to view your recommendations</p>-->
                </div>
            </div>
        </div>
        <form>
            <div class="tool-question-wrap">
                <div class="question-number-wrap">
                    <p><strong>Question {{ step }} of {{ stepTotal }}</strong></p>
                    <div class="progress-bar">
                        <div class="inner-progress-bar" :style="innerProgressStyle"></div>
                    </div>
                    <p class="progress-percent">Progress: <span v-model="progressNum">{{ progressNum }}%</span></p>
                </div>
                <div v-if="step === 1">

                    <h1>{{ step }}. Enterprise Risk Management</h1>
                    <p><strong>Definition:</strong> <em>Systems, procedures and risk assessments used by organizations to identify and plan for strategic, operational and IT risks.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for enterprise risk management.</p>
                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.enterpriseRiskManagement" value="1" @click.prevent="updateField('enterpriseRiskManagement', $event.target.value)">
                            <p>Risk management policy, principles and techniques owned at the site or facility level. Reporting of recordable incidents to corporate HQ.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.enterpriseRiskManagement" value="2" @click.prevent="updateField('enterpriseRiskManagement', $event.target.value)">
                            <p>Risk management policy determined centrally with techniques and tools determined at site level. Corporate risk register in addition to recordables reporting.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.enterpriseRiskManagement" value="3" @click.prevent="updateField('enterpriseRiskManagement', $event.target.value)">
                            <p>Enterprise risk management framework  agreed between HQ and sites. Implementation ongoing for &#60;1 year. Includes a framework to identify and manage process-related risks (e.g. spills, leaks, fires or explosions). 
</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.enterpriseRiskManagement" value="4" @click.prevent="updateField('enterpriseRiskManagement', $event.target.value)">
                            <p>Enterprise risk management framework  considers process safety risks. It is agreed between HQ and sites. Implementation complete.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.enterpriseRiskManagement" value="5" @click.prevent="updateField('enterpriseRiskManagement', $event.target.value)">
                            <p>Enterprise risk management framework considers process safety risks. It is agreed between HQ and sites. Implementation complete. Continuous monitoring and reporting supported by an information management system.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap" style="justify-content: flex-end;">
                        <button v-if="ortool.enterpriseRiskManagement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 2">

                    <h1>{{ step }}. Risk Management Data &amp; Analytics</h1>
                    <p><strong>Definition:</strong> <em>The management and analysis of data on risk across an organization. This could include real-time risk reporting and visualization tools.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for risk management data &amp; analytics.</p>

                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.riskManagementDataAnalytics" value="1" @click.prevent="updateField('riskManagementDataAnalytics', $event.target.value)">
                            <p>Risk management data stored in data silos at site or facility level. No direct access for other employees.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.riskManagementDataAnalytics" value="2" @click.prevent="updateField('riskManagementDataAnalytics', $event.target.value)">
                            <p>Majority of risk management data stored in data silos at site or facility-level. Sites contribute to corporate risk register. Analysis performed in spreadsheets. </p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.riskManagementDataAnalytics" value="3" @click.prevent="updateField('riskManagementDataAnalytics', $event.target.value)">
                            <p>Risk data consolidated in divisional and/or corporate-level database (warehouse or data lake) providing direct access for different stakeholders.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.riskManagementDataAnalytics" value="4" @click.prevent="updateField('riskManagementDataAnalytics', $event.target.value)">
                            <p>Asset-level risk models defined and data integrated from different sources. Analysis performed using software as well as spreadsheets. Access for multiple stakeholders.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.riskManagementDataAnalytics" value="5" @click.prevent="updateField('riskManagementDataAnalytics', $event.target.value)">
                            <p>Asset-level risk models utilize predictive analytics and digital twin simulations to anticipate risks (including process-related risks such as leaks or spills) and strengthen risk controls.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.riskManagementDataAnalytics" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 3">

                    <h1>{{ step }}.  Barrier Risk Management</h1>
                    <p><strong>Definition:</strong> <em>The implementation and management of barriers that are designed to prevent undesirable incidents from occurring or limit their consequences. This can include a bowtie analysis to show a visual risk assessment and structure to monitor the barriers.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for barrier risk management.</p>

                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.barrierRiskManagement" value="1" @click.prevent="updateField('barrierRiskManagement', $event.target.value)">
                            <p>Risk control information held in paper format and site-level documentation which needs to be manually accessed.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.barrierRiskManagement" value="2" @click.prevent="updateField('barrierRiskManagement', $event.target.value)">
                            <p>Internally developed or commercial barrier risk management point solutions deployed for some assets. No consistency across assets.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.barrierRiskManagement" value="3" @click.prevent="updateField('barrierRiskManagement', $event.target.value)">
                            <p>All large assets with significant hazards have commercial barrier risk management software deployed with standard definitions and controls.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.barrierRiskManagement" value="4" @click.prevent="updateField('barrierRiskManagement', $event.target.value)">
                            <p>Barrier risk management software is integrated with maintenance systems and control of work systems to provide insight into risk interdependencies.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.barrierRiskManagement" value="5" @click.prevent="updateField('barrierRiskManagement', $event.target.value)">
                            <p>Operational data from equipment condition monitors and mobile apps used by workers are fed into the barrier risk model. Digital twin simulation applied to complex assets to anticipate risks and strengthen risk controls.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.barrierRiskManagement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 4">

                    <h1>{{ step }}. Mechanical Integrity Management</h1>
                    <p><strong>Definition:</strong> <em>The management of critical process equipment to ensure equipment is installed, operated and maintained in a way to optimize reliability and safety.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for mechanical integrity management.</p>


                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mechanicalIntegrityManagement" value="1" @click.prevent="updateField('mechanicalIntegrityManagement', $event.target.value)">
                            <p>Maintenance is scheduled and monitored with local log books and spreadsheets.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mechanicalIntegrityManagement" value="2" @click.prevent="updateField('mechanicalIntegrityManagement', $event.target.value)">
                            <p>Most sites have implemented computerized maintenance management software which is used to schedule work and record completed tasks.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mechanicalIntegrityManagement" value="3" @click.prevent="updateField('mechanicalIntegrityManagement', $event.target.value)">
                            <p>All sites have asset performance management (APM) software with maintenance management and mechanical integrity reporting.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mechanicalIntegrityManagement" value="4" @click.prevent="updateField('mechanicalIntegrityManagement', $event.target.value)">
                            <p>APM software is integrated with barrier risk management software to provide analysis of maintenance-related risks.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mechanicalIntegrityManagement" value="5" @click.prevent="updateField('mechanicalIntegrityManagement', $event.target.value)">
                            <p>APM software is integrated with remote equipment monitoring systems to provide predictive insights on operational performance and maintenance requirements of assets.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.mechanicalIntegrityManagement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 5">

                    <h1>{{ step }}. Mobile Workforce Enablement</h1>
                    <p><strong>Definition:</strong> <em>Mobile devices and apps that enable authorized workers to access mobile functionality when out in the field.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for mobile workforce enablement.</p>


                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mobileWorkforceEnablement" value="1" @click.prevent="updateField('mobileWorkforceEnablement', $event.target.value)">
                            <p>Workers are not permitted (due to hazard restrictions) or unable (due to lack of connectivity) to use mobile devices on site.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mobileWorkforceEnablement" value="2" @click.prevent="updateField('mobileWorkforceEnablement', $event.target.value)">
                            <p>Authorized workers can use mobile devices in unrestricted zones only and/or in offline mode.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mobileWorkforceEnablement" value="3" @click.prevent="updateField('mobileWorkforceEnablement', $event.target.value)">
                            <p>Authorized workers with approved and/or intrinsically safe mobile devices can use them for up to 3 processes offline.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mobileWorkforceEnablement" value="4" @click.prevent="updateField('mobileWorkforceEnablement', $event.target.value)">
                            <p>Authorized workers with approved and/or intrinsically safe mobile devices can use them for up to 3 processes online.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.mobileWorkforceEnablement" value="5" @click.prevent="updateField('mobileWorkforceEnablement', $event.target.value)">
                            <p>Mobile devices can push real-time information and alerts to workers. Workers can input data into intuitive apps while out in the field.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.mobileWorkforceEnablement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 6">

                    <h1>{{ step }}. Incident Management</h1>
                    <p><strong>Definition:</strong> <em>Activities undertaken by workers, managers and executives to track, report, investigate and analyse incidents which could negatively impact workers, operations and physical assets.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for incident management.</p>


                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.incidentManagement" value="1" @click.prevent="updateField('incidentManagement', $event.target.value)">
                            <p>Incident information is captured on paper forms and stored in a site-level spreadsheet without access for other stakeholders.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.incidentManagement" value="2" @click.prevent="updateField('incidentManagement', $event.target.value)">
                            <p>Most sites provide access to incident information via an online portal (e.g. SharePoint) or through a monthly standardized report.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.incidentManagement" value="3" @click.prevent="updateField('incidentManagement', $event.target.value)">
                            <p>Most sites use commercial software for incident reporting and data storage with the ability for other stakeholders to download and review the information.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.incidentManagement" value="4" @click.prevent="updateField('incidentManagement', $event.target.value)">
                            <p>All sites with material EHS risks use the same incident management software with consistent reporting forms, data models and user interface.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.incidentManagement" value="5" @click.prevent="updateField('incidentManagement', $event.target.value)">
                            <p>Mobile applications for incident reports and safety observations provide additional data to enhance risk assessments and predictive analytics.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.incidentManagement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 7">

                    <h1>{{ step }}. Control of Work</h1>
                    <p><strong>Definition:</strong> <em>Systems, procedures and risk assessments that establish maintenance processes in operational environments to maximize worker safety and operational uptime.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for control of work.</p>


                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.controlOfWork" value="1" @click.prevent="updateField('controlOfWork', $event.target.value)">
                            <p>Data on maintenance schedules, job hazard analysis, permits to work, isolation and shift handover all managed separately with co-ordination by site supervisors.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.controlOfWork" value="2" @click.prevent="updateField('controlOfWork', $event.target.value)">
                            <p>Some sites have a single software application that links JHA, permit to work, isolation management and management of change.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.controlOfWork" value="3" @click.prevent="updateField('controlOfWork', $event.target.value)">
                            <p>All sites have a single software application that links JHA, permit to work, isolation management and management of change.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.controlOfWork" value="4" @click.prevent="updateField('controlOfWork', $event.target.value)">
                            <p>Risk management software application provides a single view of work activities at a site to identify potential hazards caused by simultaneous work being undertaken.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.controlOfWork" value="5" @click.prevent="updateField('controlOfWork', $event.target.value)">
                            <p>Risk management software application models risk interdependencies across all control of work activities. Software provides organization-wide visibility on all change requests. Supervisors able to drag and drop work activities to improve barrier health.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.controlOfWork" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 8">

                    <h1>{{ step }}. Contractor Risk Management</h1>
                    <p><strong>Definition:</strong> <em>Systems, procedures and risk assessments used to control the risks associated managing and employing contractors.</em></p>
                    <p>Select the appropriate cell that best reflects your firms current practices for contractor risk management.</p>


                    <div class="picker-wrap">
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.contractorRiskManagement" value="1" @click.prevent="updateField('contractorRiskManagement', $event.target.value)">
                            <p>Contractor information is captured on paper forms and stored in site-level spreadsheets without access for other stakeholders across the enterprise.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.contractorRiskManagement" value="2" @click.prevent="updateField('contractorRiskManagement', $event.target.value)">
                            <p>Some sites have a single software application that links data on contractors, training records and JHA to verify workers meet minimum requirements and identify required training and equipment.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.contractorRiskManagement" value="3" @click.prevent="updateField('contractorRiskManagement', $event.target.value)">
                            <p>Most sites use commercial software for contractor safety management with the ability for other stakeholders to download and review the information.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.contractorRiskManagement" value="4" @click.prevent="updateField('contractorRiskManagement', $event.target.value)">
                            <p>All sites use integrated tools to manage pre-qualification checks, job hazard analysis, training session record keeping, tracking of safety metrics and post-job evaluation.</p>
                        </div>
                        <div class="pick-item">
                            <input type="radio" v-model="ortool.contractorRiskManagement" value="5" @click.prevent="updateField('contractorRiskManagement', $event.target.value)">
                            <p>Software solutions support the continuous monitoring of contractor performance, incidents and accidents. There is a real-time, time bi-directional flow of data between contractor software solutions and safety and risk management systems.</p>
                        </div>
                    </div>

                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="ortool.contractorRiskManagement" class="continue-submit" @click.prevent="next()">Continue</button>
                    </div>

                </div>
                <div v-if="step === 9">
                    <h2 style="width: 500px;margin: 10px auto 20px;text-align: center;line-height: 1.4;">Complete your information to receive your results and recommendations!</h2>
                    <full-pardot-form />
                    <div class="btn-nav-wrap">
                        <button class="previous" @click.prevent="prev()">Previous</button>
                        <button v-if="pardotinfo.firstname && pardotinfo.lastname && pardotinfo.email && pardotinfo.phone && pardotinfo.firstname && pardotinfo.company && pardotinfo.jobtitle && pardotinfo.industry && pardotinfo.country" class="continue-submit" @click.prevent="submit()">Submit</button>
                        <button class="previous" v-else disabled style="cursor: default">*Please finish form*</button>
                    </div>
                </div>

            </div>
        </form>
    </div>
</template>

<script>
    import FullPardotForm from "../../components/FullPardotForm";
    import axios from 'axios'

    export default {
        components: {FullPardotForm},
        name: "index",
        data() {
            return {
                step: 1,
                stepTotal: 9,
                progressNum: 11,
                ortool: this.$store.state.ortool,
                pardotinfo: this.$store.state.pardotinfo
            }
        },
        methods: {
            prev() {
                this.step--;
            },
            next() {
                this.step++;
            },
            updateField(field, value) {
                this.$store.commit('updateortool', {
                    [field]: value
                });
            },
            submit() {
                let self = this;

                axios.post('https://or-maturity-model-sphera.firebaseio.com/posts.json', this.$store.state)
                    .then(result => {
                    return {
                        post: result.data
                    }
                }).then(function(result) {
                        self.$store.commit('updateortool', {
                            ID: result.post.name
                        });
                    // updateField('ID', result.post.name);
                    // self.$store.commit('updateID', result.post.name);
                    // self.$store.state.ortool.ID = result.post.name;
                    self.$router.push('result?id=' + result.post.name);
                })
                    .catch(e => console.log(e))
            }
        },
        watch: {
            step(newVal) {
                this.progressNum = ((newVal/this.stepTotal)*100).toFixed(0)
            }
        },
        computed: {
            innerProgressStyle: function() {
                return {
                    'width': this.progressNum + '%',
                    height: '4px',
                    backgroundColor: '#009bde',
                    borderRadius: '2px'
                }
            }
        }
    }
</script>

<style scoped>
    .or-maturity-wrap {
        width: 100%;
        margin: 0 auto;
    }
    .or-maturity-title {
        width: 100%;
        color: #fff;
        margin: 0 auto;
        padding: 80px 10px;
        background: url('~/assets/OR-Maturity-Model-Header.jpg') 50% 50% no-repeat;
        background-size: cover;
    }
    .or-maturity-title .holder {
        margin: 0 auto;
        width: 1150px;
    }
    .or-maturity-title .svg-bg {
        padding: 8px;
        background: #dd655c;
        margin: -15px 20px 20px;
        display: inline-block;
        border-radius: 100%;
        vertical-align: top;
    }
    .or-maturity-title img {
        display: block;
        height: 55px;
        width: 55px;
    }
    .or-maturity-title .text-content {
         display: inline-block;
         max-width: 90%;
         width: 550px;
     }
    .or-maturity-title .text-content h1 {
        line-height: 1.26;
        color: #fff;
        font-weight: 700;
        font-size: 2.25em;
    }
    .or-maturity-title .text-content h2 {
        line-height: 1.26;
        font-weight: 300;
        font-size: 1.85em;
        margin-bottom: 20px;
    }
    .or-maturity-title .text-content p {
        line-height: 1.5;
        font-weight: 500;
    }
    form {
        width: 100%;
        padding: 50px 10px;
        margin: 0 auto;
        background: #f5f5f5;
    }
    form .tool-question-wrap {
        width: 1250px;
        max-width: 100%;
        margin: 0 auto;
        position: relative;
    }
    form .tool-question-wrap div h1 {
        padding-top: 60px;
        color: rgba(0,0,0,0.85);
        font-size: 26px;
        font-weight: 700;
    }
    form .tool-question-wrap div p {
        color: #4a4a4a;
        margin-bottom: 10px;
    }
    .question-number-wrap {
        width: 200px;
        right: 0;
        top: 0;
        position: absolute;
    }
    .question-number-wrap .progress-percent {
        text-align: right;
        font-size: 10px;
        color: #4a4a4a;
        padding: 10px 0;
    }
    .btn-nav-wrap {
        width: 90%;
        margin: 0 auto;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 50px 0;
        min-height: 138px;
    }
    .btn-nav-wrap button {
        padding: 10px;
        width: 150px;
        border: 1px solid #d8d8d8;
        font-weight: 500;
        letter-spacing: 0.2px;
        font-size: 14px;
        border-radius: 5px;
        cursor: pointer;
        background: #d8d8d8;
        color: #000;
        transition: 0.15s all ease-in-out;
    }
    .btn-nav-wrap button:hover, .btn-nav-wrap button:focus, .btn-nav-wrap button:active {
        background: #f2f2f2;
        border: 1px solid #000;
    }
    button.continue-submit {
        background: #3b4;
        color: #fff;
        padding: 10px;
        width: 150px;
        border: 1px solid #3b4;
        font-weight: 500;
        letter-spacing: 0.2px;
        font-size: 14px;
        border-radius: 5px;
        cursor: pointer;
        transition: 0.15s all ease-in-out;
    }
    button.continue-submit:hover, button.continue-submit:focus, button.continue-submit:active {
        background: #f2f2f2;
        border: 1px solid #3b4;
        color: #3b4;
    }
    .btn-nav-wrap button.continue-submit {
        background: #3b4;
        color: #fff;
    }
    .btn-nav-wrap button.continue-submit:hover, .btn-nav-wrap button.continue-submit:focus, .btn-nav-wrap button.continue-submit:active {
        background: #f2f2f2;
        border: 1px solid #3b4;
        color: #3b4;
    }
    .picker-wrap {
        width: 100%;
        margin: 0 auto;
        text-align: center;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
    }
    .picker-wrap .pick-item {
        padding: 20px;
        background: #fff;
        color: rgba(132,132,132,0.9);
        width: 235px;
        min-height: 215px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: 10px;
        box-shadow: 0 0 7px 0 rgba(0, 0, 0, 0.15);
        border-radius: 5px;
        position: relative;
    }
    .picker-wrap .pick-item input {
        position: absolute;
        top: 5px;
        right: 5px;
        height: 20px;
        width: 20px;
    }
    form .picker-wrap .pick-item p {
        color: rgba(132,132,132,0.9);
        margin: 0 auto;
        max-width: 100%;
    }
    .progress-bar {
        width: 200px;
        height: 4px;
        border-radius: 2px;
        background: #bbb;
    }
</style>

