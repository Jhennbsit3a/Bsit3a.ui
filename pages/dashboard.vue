<template>
    <v-card class="mt-4">
        <v-card-title>
            <h1>Dashboard</h1>
            <v-spacer />
            <v-col md="4">
                <v-text-field
                    v-model="search"
                    append-icon="mdi-magnify"
                    label="Search"
                    single-line
                    hide-details   
                    >
                </v-text-field>
            </v-col>
        </v-card-title>
        <v-data-table :headers="headers" :items="students" :search="search">
            <template slot="item.action" slot-scope="{  }">
                <v-btn class="primary">EDIT</v-btn>
                <v-btn class="error">DELETE</v-btn>
            </template>        
        </v-data-table>
    </v-card>
</template>

<script>
export default {
    data() {
        return {
            search: '',
            headers: [
                { text:'STUDENT ID', align: 'start', filterable: false, value:'studentID'},
                { text:'LASTNAME', value:'lastName'},
                { text:'FIRSTNAME', value:'firstName'},
                { text:'MIDDLENAME', value:'middleName'},
                { text:'COURSE', value:'course'},
                { text:'SECTION', value:'section'},
                { text:'', value:'action'},
            ],
            students: [
                {
                    studentID: '21-00194',
                    lastName: 'SOLIS',
                    firstName: 'JENNYLYN',
                    middleName: 'PANGILINAN',
                    course: 'BSIT',
                    section: '3A',
                },
                {
                    studentID: '22-00009',
                    lastName: 'ESGUERRA',
                    firstName: 'JERDY',
                    middleName: 'BLOOMFIELD',
                    course: 'BSIT',
                    section: '3A',
                },
                {
                    studentID: '21-00710',
                    lastName: 'NOGOY',
                    firstName: 'MIKE',
                    middleName: 'SAMIA',
                    course: 'BSIT',
                    section: '3A',
                },
                {
                    studentID: '20-00603',
                    lastName: 'PINEDA',
                    firstName: 'GHIO',
                    middleName: 'MANALILI',
                    course: 'BSIT',
                    section: '3A',
                }
                
            ]
        }
    },
}
</script>
