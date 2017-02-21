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
        return '<b>Details:</b> '+d.Type+'<br><br><b>Business Unit: </b>'+d.business_unit+'<br><br><b>Real Estate Project: </b>'+d.PPD_Project_Name'<b>Industrial Revenue Bond Project:</b> '+d.IRB_Project_Name+'<br><br><b>More Information: </b>'+d.#_of_names;
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
                { "data": "Job Creation"}
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

<iframe src="https://octo.quickbase.com/db/bmit475rv?a=q&qid=8&dlta=pr~fl14.15.53.11.49.56.52.20.21.22.23.~&ridlist=13694" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="1000px" width="900px"></iframe>


<br>

