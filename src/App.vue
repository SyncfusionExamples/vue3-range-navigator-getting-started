<template>
      <ejs-rangenavigator :valueType='valueType' :value='value' :labelFormat='labelFormat'>
          <e-rangenavigator-series-collection>
              <e-rangenavigator-series :dataSource='data' type='StepLine' xName='Date' yName='Close' width=2>
              </e-rangenavigator-series>
          </e-rangenavigator-series-collection>
      </ejs-rangenavigator>
</template>

<script>
import { RangeNavigatorComponent, StepLineSeries, DateTime, RangenavigatorSeriesCollectionDirective,
RangenavigatorSeriesDirective } from "@syncfusion/ej2-vue-charts";

export default {
    name: "App",
    components: {
    "ejs-rangenavigator": RangeNavigatorComponent,
    "e-rangenavigator-series-collection": RangenavigatorSeriesCollectionDirective,
    "e-rangenavigator-series":  RangenavigatorSeriesDirective
  },
  data() {
    return {
     valueType: 'DateTime',
     value: [new Date("2008-01-01"), new Date("2010-01-01")],
     labelFormat: 'MMM-yy',
     data:[
        { Date: new Date("2005-01-01"), Close: 21 },
        { Date: new Date("2006-01-01"), Close: 24 },
        { Date: new Date("2007-01-01"), Close: 36 },
        { Date: new Date("2008-01-01"), Close: 38 },
        { Date: new Date("2009-01-01"), Close: 54 },
        { Date: new Date("2010-01-01"), Close: 57 },
        { Date: new Date("2011-01-01"), Close: 62 },
      ],
    };
  },
  provide: {
    rangeNavigator: [ DateTime, StepLineSeries ],
  },
};
</script>