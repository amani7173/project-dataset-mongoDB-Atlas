# project-dataset-mongoDB-Atlas
we take dataset from kaggel website and we use query to filter data on mongoDB Atlas (connect to cluster)
then make vizulization on Exel

pipline :
[
    {
        '$project': {
            'Gender': 1, 
            'Total': 1, 
            'Branch': 1
        }
    }, {
        '$group': {
            '_id': {
                'Branch': '$Branch', 
                'Gender': '$Gender'
            }, 
            'agv_total_for_each_branch': {
                '$avg': '$Total'
            }, 
            'Gender': {
                '$sum': 1
            }
        }
    }
]
