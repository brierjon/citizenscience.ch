<i18n>
{
  "en": {

    "button-overview": "Overview",

    "brownbag-info-heading": "Brown Bag Lunches",
    "brownbag-info-text": "The Brown Bag Lunches series has become a regular occasion to meet the research community, and a good setting to discuss and learn about the various approaches to Citizen Science and related projects and activities. Our agenda this year includes updates on the Center, presenters from the local Citizen Science community, and international guests.",
    "brownbag-register-text": "<b>Please register via E-Mail:</b>",

    "ringvorlesung-info-heading": "Ringvorlesung Partizipative Wissenschaftsakademie",
    "ringvorlesung-info-text-1": "«Citizen Science» und andere partizipative Forschungsansätze bekommen seit einigen Jahren immer grössere Aufmerksamkeit. Nicht zuletzt haben technologische Entwicklungen zu einem Boom in der Bürgerwissenschaft geführt. Die Ziele der Einbeziehung von Bürgerinnen und Bürgern in die Wissenschaft sind vielfältig und reichen von der Stärkung benachteiligter Gruppen bis hin zur Vergrösserung von Datenbeständen.",
    "ringvorlesung-info-text-2": "In der Ringvorlesung diskutieren wir, was Citizen Science als Teil einer transformativen Wissenschaft ausmacht. Referent*innen und Diskutant*innen aus unterschiedlichen Disziplinen hinterfragen: Wie kann Citizen Science zu gesellschaftlich relevanter Forschung beitragen? Welches Potenzial haben partizipative Ansätze um den Dialog zwischen Gesellschaft und Forschung zu stärken? Was bedeutet exzellente Forschung für Citizen Science Projekte?",
    "ringvorlesung-info-text-3": "Ziel der Ringvorlesung ist es, ein differenziertes Verständnis des Konzeptes Citizen Science und dessen transformativem Potenzial zu diskutieren. Die Ringvorlesung wird von der Partizipativen Wissenschaftsakademie gemeinsam mit dem Citizen Science Center Zürich organisiert."

    },
  "de": {

    "button-overview": "Zur Übersicht",

    "brownbag-info-heading": "Brown Bag Lunches",
    "brownbag-info-text": "The Brown Bag Lunches series has become a regular occasion to meet the research community, and a good setting to discuss and learn about the various approaches to Citizen Science and related projects and activities. Our agenda this year includes updates on the Center, presenters from the local Citizen Science community, and international guests.",
    "brownbag-register-text": "<b>Please register via E-Mail:</b>",

    "ringvorlesung-info-heading": "Ringvorlesung Partizipative Wissenschaftsakademie",
    "ringvorlesung-info-text-1": "«Citizen Science» und andere partizipative Forschungsansätze bekommen seit einigen Jahren immer grössere Aufmerksamkeit. Nicht zuletzt haben technologische Entwicklungen zu einem Boom in der Bürgerwissenschaft geführt. Die Ziele der Einbeziehung von Bürgerinnen und Bürgern in die Wissenschaft sind vielfältig und reichen von der Stärkung benachteiligter Gruppen bis hin zur Vergrösserung von Datenbeständen.",
    "ringvorlesung-info-text-2": "In der Ringvorlesung diskutieren wir, was Citizen Science als Teil einer transformativen Wissenschaft ausmacht. Referent*innen und Diskutant*innen aus unterschiedlichen Disziplinen hinterfragen: Wie kann Citizen Science zu gesellschaftlich relevanter Forschung beitragen? Welches Potenzial haben partizipative Ansätze um den Dialog zwischen Gesellschaft und Forschung zu stärken? Was bedeutet exzellente Forschung für Citizen Science Projekte?",
    "ringvorlesung-info-text-3": "Ziel der Ringvorlesung ist es, ein differenziertes Verständnis des Konzeptes Citizen Science und dessen transformativem Potenzial zu diskutieren. Die Ringvorlesung wird von der Partizipativen Wissenschaftsakademie gemeinsam mit dem Citizen Science Center Zürich organisiert."

    }
}
</i18n>
<template>
  <div>

      <app-content-section>
          <div class="content-wrapper">
              <div class="row row-centered scroll-effect">
                  <div class="col col-large-8 col-xlarge-6" v-if="event">

                      <div class="centered margin-bottom">
                          <router-link to="/events" tag="button" class="button button-secondary button-secondary-naked button-icon">
                              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M159.69,239l136-136a23.9,23.9,0,0,1,33.9,0l22.6,22.6a23.9,23.9,0,0,1,0,33.9L255.89,256l96.4,96.4a23.9,23.9,0,0,1,0,33.9L329.69,409a23.9,23.9,0,0,1-33.9,0l-136-136a23.93,23.93,0,0,1-.1-34Z"/></svg>
                              {{$t('button-overview')}}
                          </router-link>
                      </div>

                      <div class="event-details">

                          <p class="centered">
                            <img :src="'/img/events/'+event.image" style="width: 50%; border-radius:50%"/>
                          </p>

                          <h2 class="heading centered" v-html="event.title"></h2>

                          <p class="lead centered event-date">{{eventDisplayDate(event.start,event.end)}}</p>

                          <div class="margin-bottom">
                              <div class="event-speakers" v-if="event.speakers !== ''">
                                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M256,256A128,128,0,1,0,128,128,128,128,0,0,0,256,256Zm89.6,32H328.9a174.08,174.08,0,0,1-145.8,0H166.4A134.43,134.43,0,0,0,32,422.4V464a48,48,0,0,0,48,48H432a48,48,0,0,0,48-48V422.4A134.43,134.43,0,0,0,345.6,288Z"/></svg>
                                  <p v-html="event.speakers"></p>
                              </div>

                              <div class="event-location">
                                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M236.27,501.67C91,291,64,269.41,64,192,64,86,150,0,256,0S448,86,448,192c0,77.41-27,99-172.27,309.67a24,24,0,0,1-39.46,0ZM256,272a80,80,0,1,0-80-80A80,80,0,0,0,256,272Z"/></svg>
                                  <p v-html="event.location"></p>
                              </div>
                          </div>

                          <div v-if="event.content !== ''" v-html="event.content" class="margin-bottom"></div>


                          <div v-if="event.path.indexOf('brownbag') !== -1">
                              <p class="reduced-bottom-margin centered" v-html="$t('brownbag-register-text')"></p>
                              <div class="margin-bottom centered">
                                  <button class="button button-primary button-icon button-normal-case" @click="openInNewTab('mailto:info@citizenscience.ch')">
                                      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M502.3,190.8a6,6,0,0,1,9.7,4.7V400a48,48,0,0,1-48,48H48A48,48,0,0,1,0,400V195.6a6,6,0,0,1,9.7-4.7c22.4,17.4,52.1,39.5,154.1,113.6,21.1,15.4,56.7,47.8,92.2,47.6,35.7.3,72-32.8,92.3-47.6C450.3,230.4,479.9,208.2,502.3,190.8ZM256,320c23.2.4,56.6-29.2,73.4-41.4,132.7-96.3,142.8-104.7,173.4-128.7A23.93,23.93,0,0,0,512,131V112a48,48,0,0,0-48-48H48A48,48,0,0,0,0,112v19a24.08,24.08,0,0,0,9.2,18.9c30.6,23.9,40.7,32.4,173.4,128.7,16.8,12.2,50.2,41.8,73.4,41.4Z"/></svg>
                                      info@citizenscience.ch
                                  </button>
                              </div>
                              <div class="event-info">
                                  <h3 class="subheading" v-html="$t('brownbag-info-heading')"></h3>
                                  <p class="reduced-bottom-margin" v-html="$t('brownbag-info-text')"></p>
                              </div>
                          </div>

                          <div class="event-info" v-if="event.path.indexOf('ringvorlesung') !== -1">
                              <h3 class="subheading" v-html="$t('ringvorlesung-info-heading')"></h3>
                              <p class="reduced-bottom-margin" v-html="$t('ringvorlesung-info-text-1')"></p>
                              <p class="reduced-bottom-margin" v-html="$t('ringvorlesung-info-text-2')"></p>
                              <p class="reduced-bottom-margin" v-html="$t('ringvorlesung-info-text-3')"></p>
                              <button class="button button-secondary button-icon button-normal-case" @click="openInNewTab('https://www.uzh.ch/cmsssl/de/outreach/events/rv/2019hs/citizen-science.html')">
                                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 576"><path d="M576,56V184c0,21.47-26,32-41,17l-35.71-35.71L255.8,408.77a24,24,0,0,1-33.94,0l-22.63-22.63a24,24,0,0,1,0-33.94L442.76,108.68,407.05,73C392,57.9,402.66,32,424,32H552A24,24,0,0,1,576,56ZM407,302.79l-16,16a24,24,0,0,0-7,17V480H64V160H328a24,24,0,0,0,17-7l16-16c15.12-15.12,4.41-41-17-41H48A48,48,0,0,0,0,144V496a48,48,0,0,0,48,48H400a48,48,0,0,0,48-48V319.76C448,298.38,422.15,287.67,407,302.79Z"/></svg>
                                  Zur Website
                              </button>
                          </div>

                      </div>

                  </div>
              </div>
          </div>
      </app-content-section>


    <section-newsletter-signup></section-newsletter-signup>

    <app-footer :platform="platform"></app-footer>

  </div>
</template>

<script>

import ContentSection from '@/components/shared/ContentSection.vue'
import Footer from '@/components/shared/Footer.vue'
import SectionNewsletterSignup from "@/components/shared/SectionNewsletterSignup";
import Expandable from "@/components/shared/Expandable";

import events from "@/assets/events.json";

export default {
  components: {
      Expandable,
      SectionNewsletterSignup,
    'app-content-section': ContentSection,
    'app-footer': Footer
  },
    props: {
        platform: {
            type: Boolean,
            default: false
        }
    },
    metaInfo: function() {
        return {
            title: this.pageTitle,
            meta: [
                {
                    property: 'og:title',
                    content: this.pageTitle,
                    template: '%s | '+this.$t('site-title')
                },
                {
                    vmid: 'description',
                    property: 'description',
                    content: this.eventDisplayDate(this.startDate,this.endDate)
                },
                {
                    vmid: 'og:description',
                    property: 'og:description',
                    content: this.eventDisplayDate(this.startDate,this.endDate)
                },
                {
                    vmid: 'og:image',
                    property: 'og:image',
                    content: 'https://citizenscience.ch/img/events/'+this.ogImage
                }
            ]
        }
    },
    data() {
        return {
            event: undefined,
            i18nWeekdays: [
                'weekday-sunday',
                'weekday-monday',
                'weekday-tuesday',
                'weekday-wednesday',
                'weekday-thursday',
                'weekday-friday',
                'weekday-saturday',
            ],
            ogImage: undefined,
            pageTitle: undefined,
            startDate: undefined,
            endDate: undefined
        }
    },
    methods: {
        openInNewTab: function(url) {
            var win = window.open(url, '_blank');
            win.focus();
        },
        eventDisplayDate( start, end ) {
            let startDate = new Date(start);
            let endDate = new Date(end);

            if( startDate.getDate() === endDate.getDate()
                && startDate.getMonth() === endDate.getMonth()
                && startDate.getFullYear() === endDate.getFullYear() ) {
                // same day
                return this.$t(this.i18nWeekdays[startDate.getDay()]) +', '+ startDate.getDate()+'.'+(startDate.getMonth()+1)+'.'+startDate.getFullYear()+', '+startDate.getHours()+':'+(startDate.getMinutes()<10?'0':'') + startDate.getMinutes()+'–'+endDate.getHours()+':'+(endDate.getMinutes()<10?'0':'') + endDate.getMinutes();
            }
            else {
                // different day
                //console.log('different day');
                return this.$t(this.i18nWeekdays[startDate.getDay()]) +', '+ startDate.getDate()+'.'+(startDate.getMonth()+1)+'.'+startDate.getFullYear()+', '+startDate.getHours()+':'+(startDate.getMinutes()<10?'0':'') + startDate.getMinutes()+' – '+this.$t(this.i18nWeekdays[endDate.getDay()]) +', '+ endDate.getDate()+'.'+(endDate.getMonth()+1)+'.'+endDate.getFullYear()+', '+endDate.getHours()+':'+(endDate.getMinutes()<10?'0':'') + endDate.getMinutes();
            }
        }
    },
    created() {
        const self = this;
        this.event = events.find(function(element) {
            return ( element.path === self.$route.params.event );
        });

        if( !this.event ) {
            this.$router.push('/events');
        }
    },
    mounted() {
        this.ogImage = this.event.image;
        this.pageTitle = this.event.title;
        this.startDate = this.event.start;
        this.endDate = this.event.end;
    }
}

</script>

<style lang="scss">

    @import '@/styles/theme.scss';
    @import '@/styles/shared/variables.scss';

    .event-details {

        .event-speakers, .event-location {
            position: relative;
            svg {
                position: absolute;
                top: calc(( #{$font-size-normal}*1.5 - 16px ) /2);
                left: 0;
                width: 16px;
                height: 16px;
                fill: $color-secondary;
            }
            p {
                padding-left: calc( 16px + #{$spacing-2} );
            }
        }
        .event-speakers {
            margin-bottom: $spacing-2;
        }

        .event-info {
            border-radius: $border-radius;
            border: 1px solid $color-black-tint-80;
            padding: $spacing-2;
        }
    }

    @media only screen and (min-width: $viewport-mobile-large) {

        .event-details {
            .event-info {
                padding: $spacing-3;
            }
        }

    }
    @media only screen and (min-width: $viewport-tablet-portrait) {

        .event-details {
            .event-info {
                padding: $spacing-3;
            }
        }

    }
    @media only screen and (min-width: $viewport-large) {

        .event-details {
            .event-info {
                padding: $spacing-4;
            }
        }

    }
    @media only screen and (min-width: $viewport-xlarge) {

        .event-details {
            .event-info {
                padding: $spacing-5;
            }
        }

    }

</style>
