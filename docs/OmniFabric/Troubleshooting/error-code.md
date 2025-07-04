# Error Code

In OmniFabric, the error information is classified according to the error code. A specific type of error code will be unified into a specific error code for troubleshooting. All messages sent by the OmniFabric database service are assigned a five-character error code, which contains both the type of error code and the specific category of error code.

During actual use, you can first check the error code and use the text error message attached to the error code to determine what kind of error occurred. Error encodings do not change across versions and do not change due to the localization of error messages.

!!! note
    The SQL standard defines some of the error codes generated by OmniFabric; some additional error codes for conditions not defined by the standard were invented or borrowed from other databases.

|Error encoding head |Type|
|---|---|
|201|Internal Error|
|202|Number and function error|
|203|Invalid Operation|
|204|Unknown Error or IO Error|
|205|RPC Timeout|
|206|Transaction Error or Storage Engine Error|

For more information on the details of these errors, please refer to the following table:

| **Error code** | **Error number** | **Description** | **Error type** |
| --- | --- | --- | --- |
| 20100 | ErrStart | internal error code start | Internal error |
| 20101 | ErrInternal   | Internal error | Internal error |
| 20103 | ErrNYI   | not yet implemented | Internal error |
| 20104 | ErrOOM  | out of memory | Internal error |
| 20105 | ErrQueryInterrupted | query interrupted | Internal error |
| 20106 | ErrNotSupported  | not supported | Internal error |
| 20200 | ErrDivByZero | division by zero | Numbers and functions |
| 20201 | ErrOutOfRange | data out of range | Numbers and functions |
| 20202 | ErrDataTruncated  | data truncated | Numbers and functions |
| 20203 | ErrInvalidArg  | invalid argument | Numbers and functions |
| 20204 | ErrTruncatedWrongValueForField | truncated wrong value for column | Numbers and functions |
| 20300 | ErrBadConfig | invalid configuration | Invalid operation |
| 20301 | ErrInvalidInput | invalid input | Invalid operation |
| 20302 | ErrSyntaxError | SQL syntax error | Invalid operation |
| 20303 | ErrParseError | SQL parser error | Invalid operation |
| 20304 | ErrConstraintViolation | constraint violation | Invalid operation |
| 20305 | ErrDuplicate | tae data duplicated | Invalid operation |
| 20306 | ErrRoleGrantedToSelf  | cannot grant role | Invalid operation |
| 20307 | ErrDuplicateEntry | duplicate entry for key | Invalid operation |
| 20400 | ErrInvalidState | invalid state | Unknown status or I/O error |
| 20401 | ErrLogServiceNotReady | log service not ready | Unknown status or I/O error |
| 20402 | ErrBadDB | invalid database | Unknown status or I/O error |
| 20403 | ErrNoSuchTable  | no such table | Unknown status or I/O error |
| 20404 | ErrEmptyVector     | empty vector | Unknown status or I/O error |
| 20405 | ErrFileNotFound   | file is not found | Unknown status or I/O error |
| 20406 | ErrFileAlreadyExists  | file alread exists | Unknown status or I/O error |
| 20407 | ErrUnexpectedEOF | unexpteded end of file | Unknown status or I/O error |
| 20408 | ErrEmptyRange     | empty range of file | Unknown status or I/O error |
| 20409 | ErrSizeNotMatch  | file size does not match | Unknown status or I/O error |
| 20410 | ErrNoProgress | file has no io progress | Unknown status or I/O error |
| 20411 | ErrInvalidPath | invalid file path | Unknown status or I/O error |
| 20412 | ErrShortWrite | file io short write | Unknown status or I/O error |
| 20413 | ErrInvalidWrite | file io invalid write | Unknown status or I/O error |
| 20414 | ErrShortBuffer  | file io short buffer | Unknown status or I/O error |
| 20415 | ErrNoDB | not connect to a database | Unknown status or I/O error |
| 20416 | ErrNoWorkingStore   | no working store | Unknown status or I/O error |
| 20417 | ErrNoHAKeeper          | cannot locate ha keeper | Unknown status or I/O error |
| 20418 | ErrInvalidTruncateLsn | invalid truncate lsn, shard already truncated | Unknown status or I/O error |
| 20419 | ErrNotLeaseHolder         | not lease holder, current lease holder ID xxx | Unknown status or I/O error |
| 20420 | ErrDBAlreadyExists   | database already exists | Unknown status or I/O error |
| 20421 | ErrTableAlreadyExists   | table already exists | Unknown status or I/O error |
| 20422 | ErrNoService    | service not found | Unknown status or I/O error |
| 20423 | ErrDupServiceName | duplicate service name | Unknown status or I/O error |
| 20424 | ErrWrongService        | wrong service, expecting A, got B | Unknown status or I/O error |
| 20425 | ErrBadS3Config        | bad s3 config | Unknown status or I/O error |
| 20426 | ErrBadView   | invalid view | Unknown status or I/O error |
| 20427 | ErrInvalidTask    | invalid task | Unknown status or I/O error |
| 20428 | ErrInvalidServiceIndex     | invalid service idx | Unknown status or I/O error |
| 20429 | ErrDragonboatTimeout   | Dragonboat timeout | Unknown status or I/O error |
| 20430 | ErrDragonboatTimeoutTooSmall | Dragonboat timeout too small | Unknown status or I/O error |
| 20431 | ErrDragonboatInvalidDeadline | Dragonboat invalid deadline | Unknown status or I/O error |
| 20432 | ErrDragonboatRejected  | Dragonboat rejected | Unknown status or I/O error |
| 20433 | ErrDragonboatInvalidPayloadSize | invalid payload size | Unknown status or I/O error |
| 20434 | ErrDragonboatShardNotReady  | shard not ready  | Unknown status or I/O error |
| 20435 | ErrDragonboatSystemClosed | Dragonboat system closed | Unknown status or I/O error |
| 20436 | ErrDragonboatInvalidRange  | Dragonboat invalid range  | Unknown status or I/O error |
| 20437 | ErrDragonboatShardNotFound | shard not found | Unknown status or I/O error |
| 20438 | ErrDragonboatOtherSystemError | other system error | Unknown status or I/O error |
| 20439 | ErrDropNonExistsDB | Can't drop database ; database doesn't exist | Unknown status or I/O error |
| 20500 | ErrRPCTimeout | rpc timeout | RPC Timeout |
| 20501 | ErrClientClosed | client closed | RPC Timeout |
| 20502 | ErrBackendClosed | backend closed | RPC Timeout |
| 20503 | ErrStreamClosed | stream closed | RPC Timeout |
| 20504 | ErrNoAvailableBackend  | no available backend | RPC Timeout |
| 20600 | ErrTxnClosed | the transaction has been committed or aborted | Transaction |
| 20601 | ErrTxnWriteConflict | transaction write conflict | Transaction |
| 20602 | ErrMissingTxn | missing transaction | Transaction |
| 20603 | ErrUnresolvedConflict | unresolved conflict | Transaction |
| 20604 | ErrTxnError  | transaction error | Transaction |
| 20605 | ErrDNShardNotFound | TN shard not found | Transaction |
| 20606 | ErrShardNotReported  | TN shard not reported | Transaction |
| 20607 | ErrTAEError | tae error | TAE Error |
| 20608 | ErrTAERead | tae read error | TAE Error |
| 20609 | ErrRpcError | rpc error | TAE Error |
| 20610 | ErrWaitTxn | transaction wait error | TAE Error |
| 20611 | ErrTxnNotFound | transaction not found | TAE Error |
| 20612 | ErrTxnNotActive | transaction not active | TAE Error |
| 20613 | ErrTAEWrite  | tae write error | TAE Error |
| 20614 | ErrTAECommit | tae commit error | TAE Error |
| 20615 | ErrTAERollback  | tae rollback error | TAE Error |
| 20616 | ErrTAEPrepare | tae prepare error | TAE Error |
| 20617 | ErrTAEPossibleDuplicate | tae possible duplicate | TAE Error |
| 20618 | ErrTxnRWConflict | r-w conflict | TAE Error |
| 20619 | ErrTxnWWConflict  | w-w conflict | TAE Error |
| 20620 | ErrNotFound | transaction not found | TAE Error |
| 20621 | ErrTxnInternal | transaction internal error | TAE Error |
| 20622 | ErrTxnReadConflict | transaction read conflict | TAE Error |
| 20623 | ErrPrimaryKeyDuplicated | duplicated primary key | TAE Error |
| 20624 | ErrAppendableSegmentNotFound | appendable segment not found | TAE Error |
| 20625 | ErrAppendableBlockNotFound | appendable block not found | TAE Error |
| 20626 | ErrTAEDebug | TAE debug | TAE Error |
