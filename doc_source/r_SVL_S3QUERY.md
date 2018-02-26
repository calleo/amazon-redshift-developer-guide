# SVL\_S3QUERY<a name="r_SVL_S3QUERY"></a>

Use the SVL\_S3QUERY view to get details about Amazon Redshift Spectrum queries at the segment and node slice level\.

SVL\_S3QUERY is visible to all users\. Superusers can see all rows; regular users can see only their own data\. For more information, see [Visibility of Data in System Tables and Views](c_visibility-of-data.md)\.

## Table Columns<a name="r_SVL_S3QUERY-table-columns"></a>

[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/redshift/latest/dg/r_SVL_S3QUERY.html)

## Sample Query<a name="r_SVL_S3QUERY-sample-query"></a>

The following example gets the scan step details for the last query executed\.

```
select query, segment, slice, elapsed, s3_scanned_rows, s3_scanned_bytes, s3query_returned_rows, s3query_returned_bytes, files 
from svl_s3query 
where query = pg_last_query_id() 
order by query,segment,slice;
<<<<<<< HEAD
```

```
query | segment | slice | elapsed | s3_scanned_rows | s3_scanned_bytes | s3query_returned_rows | s3query_returned_bytes | files
------+---------+-------+---------+-----------------+------------------+-----------------------+------------------------+------
 4587 |       2 |     0 |   67811 |               0 |                0 |                     0 |                      0 |     0
 4587 |       2 |     1 |  591568 |          172462 |         11260097 |                  8513 |                 170260 |     1
 4587 |       2 |     2 |  216849 |               0 |                0 |                     0 |                      0 |     0
 4587 |       2 |     3 |  216671 |               0 |                0 |                     0 |                      0 |     0
=======
>>>>>>> d940ef9046cd1aeb28a5d74442d2035df797200d
```