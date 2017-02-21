---
layout: page
permalink: /
title: Accomplishments Tracker
---


<table id="accomplishment" class="display">
    <thead>
        <tr><th></th><th>Topic</th><th>Date</th><th>Job Creation</th><th>Tax Revenue</th><th>Aff. Housing</th><th>Good Gov't</th>

 
<script type="text/javascript">
    /* Formatting function for row details - modify as you need */
    function format ( d ) {
    // `d` is the original data object for the row
        return '<b>Details:</b> '+d.Details+'<br><br><b>Business Unit: </b>'+d.Business_Unit+'<br><br><b>Real Estate Project: </b>'+d.PPD_Project_Name+'<b>Industrial Revenue Bond Project:</b> '+d.IRB_Project_Name+'<br><br><b>More Information: </b>'+d.Number_of_Links;
        }

    $(document).ready( function() {
        var table = $('#accomplishment').dataTable( {
            "ajax": "{{ site.baseurl }}/assets/data/accomplishments.json",
            "columns": [
                {
                    "class":          "details-control",
                    "orderable":      false,
                    "data":           null,
                    "defaultContent": "+"
                },
                { "data": "Topic"},
                { "data": "Date"},
                { "data": "Job Creation"},
                { "data": "Tax Revenue"},
                { "data": "Aff. Housing"},
                { "data": "Good Gov't"}
            ]
        } );

        // Add event listener for opening and closing details
        $('#accomplishment tbody').on('click', 'td.details-control', function () {
            var tr = $(this).closest('tr');
            var row = table.api().row( tr );
             
            if ( row.child.isShown() ) {
                // This row is already open - close it
                row.child.hide();
                tr.removeClass('shown');
            }
            else {
                // Open this row
                row.child( format(row.data()) ).show();
                tr.addClass('shown');
            }
        } );
    } );
</script>



<br>

