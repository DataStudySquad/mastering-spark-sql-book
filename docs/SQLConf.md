# SQLConf &mdash; Internal Configuration Store

`SQLConf` is an internal **configuration store** for [parameters and hints](#parameters) used in Spark SQL.

!!! important
    `SQLConf` is an internal part of Spark SQL and is not supposed to be used directly. Spark SQL configuration is available through the user-facing [RuntimeConfig](spark-sql-RuntimeConfig.md).

`SQLConf` offers methods to <<get, get>>, <<set, set>>, <<unset, unset>> or <<clear, clear>> values of configuration properties, but has also the <<accessor-methods, accessor methods>> to read the current value of a configuration property or hint.

## <span id="MAX_TO_STRING_FIELDS"><span id="histogramEnabled"> histogramEnabled

The value of [spark.sql.statistics.histogram.enabled](spark-sql-properties.md#spark.sql.statistics.histogram.enabled) configuration property

Used when [AnalyzeColumnCommand](logical-operators/AnalyzeColumnCommand.md) logical command is executed.

## <span id="MAX_TO_STRING_FIELDS"><span id="maxToStringFields"> maxToStringFields

The value of [spark.sql.debug.maxToStringFields](spark-sql-properties.md#spark.sql.debug.maxToStringFields) configuration property

## <span id="ADAPTIVE_EXECUTION_ENABLED"><span id="adaptiveExecutionEnabled"> adaptiveExecutionEnabled

The value of [spark.sql.adaptive.enabled](spark-sql-properties.md#spark.sql.adaptive.enabled) configuration property

Used when:

* `AdaptiveSparkPlanHelper` is requested to `getOrCloneSessionWithAqeOff`

* [InsertAdaptiveSparkPlan](physical-optimizations/InsertAdaptiveSparkPlan.md) and [EnsureRequirements](physical-optimizations/EnsureRequirements.md) physical optimizations are executed

## <span id="DEFAULT_CATALOG"> DEFAULT_CATALOG

The value of [spark.sql.defaultCatalog](spark-sql-properties.md#spark.sql.defaultCatalog) configuration property

Used when `CatalogManager` is requested for the [current CatalogPlugin](connector/catalog/CatalogManager.md#currentCatalog)

## <span id="DYNAMIC_PARTITION_PRUNING_ENABLED"><span id="dynamicPartitionPruningEnabled"> dynamicPartitionPruningEnabled

The value of [spark.sql.optimizer.dynamicPartitionPruning.enabled](spark-sql-properties.md#spark.sql.optimizer.dynamicPartitionPruning.enabled) configuration property

Used when:

* [CleanupDynamicPruningFilters](logical-optimizations/CleanupDynamicPruningFilters.md) logical optimization rule is executed

* [PartitionPruning](logical-optimizations/PartitionPruning.md) logical optimization rule is executed

* [PlanDynamicPruningFilters](physical-optimizations/PlanDynamicPruningFilters.md) preparation physical rule is executed

## <span id="DYNAMIC_PARTITION_PRUNING_FALLBACK_FILTER_RATIO"><span id="dynamicPartitionPruningFallbackFilterRatio"> dynamicPartitionPruningFallbackFilterRatio

The value of [spark.sql.optimizer.dynamicPartitionPruning.fallbackFilterRatio](spark-sql-properties.md#spark.sql.optimizer.dynamicPartitionPruning.fallbackFilterRatio) configuration property

Used when [PartitionPruning](logical-optimizations/PartitionPruning.md) logical optimization rule is executed.

## <span id="DYNAMIC_PARTITION_PRUNING_USE_STATS"><span id="dynamicPartitionPruningUseStats"> dynamicPartitionPruningUseStats

The value of [spark.sql.optimizer.dynamicPartitionPruning.useStats](spark-sql-properties.md#spark.sql.optimizer.dynamicPartitionPruning.useStats) configuration property

Used when [PartitionPruning](logical-optimizations/PartitionPruning.md) logical optimization rule is executed.

## <span id="EXCHANGE_REUSE_ENABLED"><span id="exchangeReuseEnabled"> exchangeReuseEnabled

The value of [spark.sql.exchange.reuse](spark-sql-properties.md#spark.sql.exchange.reuse) configuration property

Used when:

* [AdaptiveSparkPlanExec](physical-operators/AdaptiveSparkPlanExec.md) physical operator is requested to [createQueryStages](physical-operators/AdaptiveSparkPlanExec.md#createQueryStages)

* [PartitionPruning](logical-optimizations/PartitionPruning.md) logical optimization rule is executed.

* `PlanDynamicPruningFilters` and [ReuseExchange](physical-optimizations/ReuseExchange.md) physical optimizations are executed

## <span id="DYNAMIC_PARTITION_PRUNING_REUSE_BROADCAST_ONLY"><span id="dynamicPartitionPruningReuseBroadcastOnly"> dynamicPartitionPruningReuseBroadcastOnly

The value of [spark.sql.optimizer.dynamicPartitionPruning.reuseBroadcastOnly](spark-sql-properties.md#spark.sql.optimizer.dynamicPartitionPruning.reuseBroadcastOnly) configuration property

Used when [PartitionPruning](logical-optimizations/PartitionPruning.md) logical optimization is executed

## <span id="OPTIMIZER_EXCLUDED_RULES"><span id="optimizerExcludedRules"> optimizerExcludedRules

The value of [spark.sql.optimizer.excludedRules](spark-sql-properties.md#spark.sql.optimizer.excludedRules) configuration property

Used when `Optimizer` is requested for the [batches](catalyst/Optimizer.md#batches)

## <span id="FETCH_SHUFFLE_BLOCKS_IN_BATCH"><span id="fetchShuffleBlocksInBatch"> fetchShuffleBlocksInBatch

The value of [spark.sql.adaptive.fetchShuffleBlocksInBatch](spark-sql-properties.md#spark.sql.adaptive.fetchShuffleBlocksInBatch) configuration property

Used when [ShuffledRowRDD](ShuffledRowRDD.md) is created

## <span id="ADAPTIVE_EXECUTION_LOG_LEVEL"><span id="adaptiveExecutionLogLevel"> adaptiveExecutionLogLevel

The value of [spark.sql.adaptive.logLevel](spark-sql-properties.md#spark.sql.adaptive.logLevel) configuration property

Used when [AdaptiveSparkPlanExec](physical-operators/AdaptiveSparkPlanExec.md) physical operator is executed

## <span id="ADAPTIVE_EXECUTION_FORCE_APPLY"> ADAPTIVE_EXECUTION_FORCE_APPLY

[spark.sql.adaptive.forceApply](spark-sql-properties.md#spark.sql.adaptive.forceApply) configuration property

Used when [InsertAdaptiveSparkPlan](physical-optimizations/InsertAdaptiveSparkPlan.md) physical optimization is executed

## <span id="NON_EMPTY_PARTITION_RATIO_FOR_BROADCAST_JOIN"><span id="nonEmptyPartitionRatioForBroadcastJoin"> nonEmptyPartitionRatioForBroadcastJoin

The value of [spark.sql.adaptive.nonEmptyPartitionRatioForBroadcastJoin](spark-sql-properties.md#spark.sql.adaptive.nonEmptyPartitionRatioForBroadcastJoin) configuration property

Used when [DemoteBroadcastHashJoin](logical-optimizations/DemoteBroadcastHashJoin.md) logical optimization is executed

## <span id="COALESCE_PARTITIONS_ENABLED"><span id="coalesceShufflePartitionsEnabled"> coalesceShufflePartitionsEnabled

The value of [spark.sql.adaptive.coalescePartitions.enabled](spark-sql-properties.md#spark.sql.adaptive.coalescePartitions.enabled) configuration property

Used when [CoalesceShufflePartitions](physical-optimizations/CoalesceShufflePartitions.md) and [EnsureRequirements](physical-optimizations/EnsureRequirements.md) physical optimizations are executed

## <span id="SORT_BEFORE_REPARTITION"><span id="sortBeforeRepartition"> sortBeforeRepartition

The value of [spark.sql.execution.sortBeforeRepartition](spark-sql-properties.md#spark.sql.execution.sortBeforeRepartition) configuration property

Used when [ShuffleExchangeExec](physical-operators/ShuffleExchangeExec.md) physical operator is executed

## <span id="RANGE_EXCHANGE_SAMPLE_SIZE_PER_PARTITION"><span id="rangeExchangeSampleSizePerPartition"> rangeExchangeSampleSizePerPartition

The value of [spark.sql.execution.rangeExchange.sampleSizePerPartition](spark-sql-properties.md#spark.sql.execution.rangeExchange.sampleSizePerPartition) configuration property

Used when [ShuffleExchangeExec](physical-operators/ShuffleExchangeExec.md) physical operator is executed

## <span id="SHUFFLE_PARTITIONS"><span id="numShufflePartitions"> numShufflePartitions

The value of [spark.sql.shuffle.partitions](spark-sql-properties.md#spark.sql.shuffle.partitions) configuration property

## <span id="SKEW_JOIN_SKEWED_PARTITION_FACTOR"> SKEW_JOIN_SKEWED_PARTITION_FACTOR

[spark.sql.adaptive.skewJoin.skewedPartitionFactor](spark-sql-properties.md#spark.sql.adaptive.skewJoin.skewedPartitionFactor) configuration property

Used when [OptimizeSkewedJoin](physical-optimizations/OptimizeSkewedJoin.md) physical optimization is executed

## <span id="SKEW_JOIN_SKEWED_PARTITION_THRESHOLD"> SKEW_JOIN_SKEWED_PARTITION_THRESHOLD

[spark.sql.adaptive.skewJoin.skewedPartitionThresholdInBytes](spark-sql-properties.md#spark.sql.adaptive.skewJoin.skewedPartitionThresholdInBytes) configuration property

Used when [OptimizeSkewedJoin](physical-optimizations/OptimizeSkewedJoin.md) physical optimization is executed

## <span id="ADVISORY_PARTITION_SIZE_IN_BYTES"> ADVISORY_PARTITION_SIZE_IN_BYTES

[spark.sql.adaptive.advisoryPartitionSizeInBytes](spark-sql-properties.md#spark.sql.adaptive.advisoryPartitionSizeInBytes) configuration property

Used when [CoalesceShufflePartitions](physical-optimizations/CoalesceShufflePartitions.md) and [OptimizeSkewedJoin](physical-optimizations/OptimizeSkewedJoin.md) physical optimizations are executed

## <span id="SKEW_JOIN_ENABLED"> SKEW_JOIN_ENABLED

[spark.sql.adaptive.skewJoin.enabled](spark-sql-properties.md#spark.sql.adaptive.skewJoin.enabled) configuration property

Used when [OptimizeSkewedJoin](physical-optimizations/OptimizeSkewedJoin.md) physical optimization is executed

## <span id="IGNORE_CORRUPT_FILES"><span id="ignoreCorruptFiles"> ignoreCorruptFiles

The value of [spark.sql.files.ignoreCorruptFiles](spark-sql-properties.md#spark.sql.files.ignoreCorruptFiles) configuration property

Used when:

* `AvroUtils` utility is requested to `inferSchema`
* `OrcFileFormat` is requested to [inferSchema](OrcFileFormat.md#inferSchema) and [buildReader](OrcFileFormat.md#buildReader)
* `FileScanRDD` is [created](rdds/FileScanRDD.md#ignoreCorruptFiles) (and then to [compute a partition](rdds/FileScanRDD.md#compute))
* `SchemaMergeUtils` utility is requested to `mergeSchemasInParallel`
* `OrcUtils` utility is requested to `readSchema`
* `FilePartitionReader` is requested to `ignoreCorruptFiles`

## <span id="IGNORE_MISSING_FILES"><span id="ignoreMissingFiles"> ignoreMissingFiles

The value of [spark.sql.files.ignoreMissingFiles](spark-sql-properties.md#spark.sql.files.ignoreMissingFiles) configuration property

Used when:

* `FileScanRDD` is [created](rdds/FileScanRDD.md#ignoreMissingFiles) (and then to [compute a partition](rdds/FileScanRDD.md#compute))
* `InMemoryFileIndex` utility is requested to [bulkListLeafFiles](InMemoryFileIndex.md#bulkListLeafFiles)
* `FilePartitionReader` is requested to `ignoreMissingFiles`

## <span id="NESTED_SCHEMA_PRUNING_ENABLED"><span id="nestedSchemaPruningEnabled"> nestedSchemaPruningEnabled

The value of [spark.sql.optimizer.nestedSchemaPruning.enabled](spark-sql-properties.md#spark.sql.optimizer.nestedSchemaPruning.enabled) configuration property

Used when [SchemaPruning](logical-optimizations/SchemaPruning.md), [ColumnPruning](logical-optimizations/ColumnPruning.md) and [V2ScanRelationPushDown](logical-optimizations/V2ScanRelationPushDown.md) logical optimizations are executed

## <span id="FILE_COMPRESSION_FACTOR"><span id="fileCompressionFactor"> fileCompressionFactor

The value of [spark.sql.sources.fileCompressionFactor](spark-sql-properties.md#spark.sql.sources.fileCompressionFactor) configuration property

Used when:

* `HadoopFsRelation` is requested for a [size](HadoopFsRelation.md#sizeInBytes)
* `FileScan` is requested to [estimate statistics](FileScan.md#estimateStatistics)

## <span id="PARTITION_OVERWRITE_MODE"><span id="partitionOverwriteMode"> partitionOverwriteMode

The value of [spark.sql.sources.partitionOverwriteMode](spark-sql-properties.md#spark.sql.sources.partitionOverwriteMode) configuration property

Used when [InsertIntoHadoopFsRelationCommand](logical-operators/InsertIntoHadoopFsRelationCommand.md) logical command is executed

## <span id="COMPRESS_CACHED"><span id="useCompression"> useCompression

The value of [spark.sql.inMemoryColumnarStorage.compressed](spark-sql-properties.md#spark.sql.inMemoryColumnarStorage.compressed) configuration property

Used when `CacheManager` is requested to [cache a structured query](CacheManager.md#cacheQuery)

## <span id="COLUMN_BATCH_SIZE"><span id="columnBatchSize"> columnBatchSize

The value of [spark.sql.inMemoryColumnarStorage.batchSize](spark-sql-properties.md#spark.sql.inMemoryColumnarStorage.batchSize) configuration property

Used when:

* `CacheManager` is requested to [cache a structured query](CacheManager.md#cacheQuery)
* `RowToColumnarExec` physical operator is requested to [doExecuteColumnar](physical-operators/RowToColumnarExec.md#doExecuteColumnar)

## <span id="MAX_RECORDS_PER_FILE"><span id="maxRecordsPerFile"> maxRecordsPerFile

The value of [spark.sql.files.maxRecordsPerFile](spark-sql-properties.md#spark.sql.files.maxRecordsPerFile) configuration property

Used when:

* `FileFormatWriter` utility is used to [write out a query result](FileFormatWriter.md#write)

## <span id="sessionLocalTimeZone"> sessionLocalTimeZone

The value of [spark.sql.session.timeZone](spark-sql-properties.md#spark.sql.session.timeZone) configuration property

## To Be Reviewed

[[accessor-methods]]
.SQLConf's Accessor Methods
[cols="1m,1,1",options="header",width="100%"]
|===
| Name
| Parameter
| Description

| autoBroadcastJoinThreshold
| spark-sql-properties.md#spark.sql.autoBroadcastJoinThreshold[spark.sql.autoBroadcastJoinThreshold]
| [[autoBroadcastJoinThreshold]] Used exclusively in [JoinSelection](execution-planning-strategies/JoinSelection.md) execution planning strategy

| autoSizeUpdateEnabled
| spark-sql-properties.md#spark.sql.statistics.size.autoUpdate.enabled[spark.sql.statistics.size.autoUpdate.enabled]
a| [[autoSizeUpdateEnabled]] Used when:

* `CommandUtils` is requested for spark-sql-CommandUtils.md#updateTableStats[updating existing table statistics]

* `AlterTableAddPartitionCommand` is executed

| avroCompressionCodec
| <<spark-sql-properties.md#spark.sql.avro.compression.codec, spark.sql.avro.compression.codec>>
| [[avroCompressionCodec]] Used exclusively when `AvroOptions` is requested for the <<spark-sql-AvroOptions.md#compression, compression>> configuration property (and it was not set explicitly)

| broadcastTimeout
| spark-sql-properties.md#spark.sql.broadcastTimeout[spark.sql.broadcastTimeout]
| [[broadcastTimeout]] Used exclusively in spark-sql-SparkPlan-BroadcastExchangeExec.md[BroadcastExchangeExec] (for broadcasting a table to executors).

| bucketingEnabled
| spark-sql-properties.md#spark.sql.sources.bucketing.enabled[spark.sql.sources.bucketing.enabled]
| [[bucketingEnabled]] Used when `FileSourceScanExec` is requested for the spark-sql-SparkPlan-FileSourceScanExec.md#inputRDD[input RDD] and to determine spark-sql-SparkPlan-FileSourceScanExec.md#outputPartitioning[output partitioning] and spark-sql-SparkPlan-FileSourceScanExec.md#outputOrdering[ordering]

| cacheVectorizedReaderEnabled
| spark-sql-properties.md#spark.sql.inMemoryColumnarStorage.enableVectorizedReader[spark.sql.inMemoryColumnarStorage.enableVectorizedReader]
| [[cacheVectorizedReaderEnabled]] Used exclusively when `InMemoryTableScanExec` physical operator is requested for [supportsBatch](physical-operators/InMemoryTableScanExec.md#supportsBatch) flag.

| caseSensitiveAnalysis
| spark-sql-properties.md#spark.sql.caseSensitive[spark.sql.caseSensitive]
a| [[caseSensitiveAnalysis]]

| cboEnabled
| spark-sql-properties.md#spark.sql.cbo.enabled[spark.sql.cbo.enabled]
a| [[cboEnabled]] Used in:

* spark-sql-Optimizer-ReorderJoin.md[ReorderJoin] logical plan optimization (and indirectly in `StarSchemaDetection` for `reorderStarJoins`)
* spark-sql-Optimizer-CostBasedJoinReorder.md[CostBasedJoinReorder] logical plan optimization

| constraintPropagationEnabled
| spark-sql-properties.md#spark.sql.constraintPropagation.enabled[spark.sql.constraintPropagation.enabled]
a| [[constraintPropagationEnabled]][[CONSTRAINT_PROPAGATION_ENABLED]] Used when:

* spark-sql-Optimizer-InferFiltersFromConstraints.md[InferFiltersFromConstraints] logical optimization is executed

* `QueryPlanConstraints` is requested for the constraints

| CONVERT_METASTORE_ORC
| hive/configuration-properties.md#spark.sql.hive.convertMetastoreOrc[spark.sql.hive.convertMetastoreOrc]
| [[CONVERT_METASTORE_ORC]] Used when `RelationConversions` logical post-hoc evaluation rule is executed (and requested to hive/RelationConversions.md#isConvertible[isConvertible])

| CONVERT_METASTORE_PARQUET
| hive/configuration-properties.md#spark.sql.hive.convertMetastoreParquet[spark.sql.hive.convertMetastoreParquet]
| [[CONVERT_METASTORE_PARQUET]] Used when `RelationConversions` logical post-hoc evaluation rule is executed (and requested to hive/RelationConversions.md#isConvertible[isConvertible])

| dataFramePivotMaxValues
| spark-sql-properties.md#spark.sql.pivotMaxValues[spark.sql.pivotMaxValues]
| [[dataFramePivotMaxValues]] Used exclusively in spark-sql-RelationalGroupedDataset.md#pivot[pivot] operator.

| dataFrameRetainGroupColumns
| spark-sql-properties.md#spark.sql.retainGroupColumns[spark.sql.retainGroupColumns]
| [[dataFrameRetainGroupColumns]] Used exclusively in spark-sql-RelationalGroupedDataset.md[RelationalGroupedDataset] when creating the result `Dataset` (after `agg`, `count`, `mean`, `max`, `avg`, `min`, and `sum` operators).

| defaultSizeInBytes
| spark-sql-properties.md#spark.sql.defaultSizeInBytes[spark.sql.defaultSizeInBytes]
a| [[defaultSizeInBytes]] Used when:

* `DetermineTableStats` logical resolution rule could not compute the table size or <<spark.sql.statistics.fallBackToHdfs, spark.sql.statistics.fallBackToHdfs>> is turned off

* spark-sql-LogicalPlan-ExternalRDD.md#computeStats[ExternalRDD], spark-sql-LogicalPlan-LogicalRDD.md#computeStats[LogicalRDD] and `DataSourceV2Relation` are requested for statistics (i.e. `computeStats`)

*  (Spark Structured Streaming) `StreamingRelation`, `StreamingExecutionRelation`, `StreamingRelationV2` and `ContinuousExecutionRelation` are requested for statistics (i.e. `computeStats`)

* `DataSource` [creates a HadoopFsRelation for FileFormat data source](DataSource.md#resolveRelation) (and builds a CatalogFileIndex when no table statistics are available)

* `BaseRelation` is requested for spark-sql-BaseRelation.md#sizeInBytes[an estimated size of this relation] (in bytes)

| enableRadixSort
| <<spark-sql-properties.md#spark.sql.sort.enableRadixSort, spark.sql.sort.enableRadixSort>>
a| [[enableRadixSort]] Used exclusively when `SortExec` physical operator is requested for a <<spark-sql-SparkPlan-SortExec.md#createSorter, UnsafeExternalRowSorter>>.

| fallBackToHdfsForStatsEnabled
| spark-sql-properties.md#spark.sql.statistics.fallBackToHdfs[spark.sql.statistics.fallBackToHdfs]
| [[fallBackToHdfsForStatsEnabled]] Used exclusively when `DetermineTableStats` logical resolution rule is executed.

| fileCommitProtocolClass
| spark-sql-properties.md#spark.sql.sources.commitProtocolClass[spark.sql.sources.commitProtocolClass]
a| [[fileCommitProtocolClass]] Used (to instantiate a `FileCommitProtocol`) when:

* `SaveAsHiveFile` is requested to <<hive/SaveAsHiveFile.md#saveAsHiveFile, saveAsHiveFile>>

* [InsertIntoHadoopFsRelationCommand](logical-operators/InsertIntoHadoopFsRelationCommand.md) logical command is executed

| filesMaxPartitionBytes
| <<spark-sql-properties.md#spark.sql.files.maxPartitionBytes, spark.sql.files.maxPartitionBytes>>
a| [[filesMaxPartitionBytes]] Used exclusively when <<spark-sql-SparkPlan-FileSourceScanExec.md#, FileSourceScanExec>> leaf physical operator is requested to <<spark-sql-SparkPlan-FileSourceScanExec.md#createNonBucketedReadRDD, create an RDD for non-bucketed reads>>

| filesOpenCostInBytes
| <<spark-sql-properties.md#spark.sql.files.openCostInBytes, spark.sql.files.openCostInBytes>>
a| [[filesOpenCostInBytes]] Used exclusively when <<spark-sql-SparkPlan-FileSourceScanExec.md#, FileSourceScanExec>> leaf physical operator is requested to <<spark-sql-SparkPlan-FileSourceScanExec.md#createNonBucketedReadRDD, create an RDD for non-bucketed reads>>

| histogramNumBins
| spark-sql-properties.md#spark.sql.statistics.histogram.numBins[spark.sql.statistics.histogram.numBins]
| [[histogramNumBins]] Used exclusively when `AnalyzeColumnCommand` is spark-sql-LogicalPlan-AnalyzeColumnCommand.md#run[executed] with spark-sql-properties.md#spark.sql.statistics.histogram.enabled[spark.sql.statistics.histogram.enabled] turned on (and spark-sql-LogicalPlan-AnalyzeColumnCommand.md#computePercentiles[calculates percentiles]).

| hugeMethodLimit
| spark-sql-properties.md#spark.sql.codegen.hugeMethodLimit[spark.sql.codegen.hugeMethodLimit]
| [[hugeMethodLimit]] Used exclusively when `WholeStageCodegenExec` unary physical operator is requested to <<spark-sql-SparkPlan-WholeStageCodegenExec.md#doExecute, execute>> (and generate a `RDD[InternalRow]`), i.e. when the compiled function exceeds this threshold, the whole-stage codegen is deactivated for this subtree of the query plan.

| inMemoryPartitionPruning
| spark-sql-properties.md#spark.sql.inMemoryColumnarStorage.partitionPruning[spark.sql.inMemoryColumnarStorage.partitionPruning]
| [[inMemoryPartitionPruning]] Used exclusively when `InMemoryTableScanExec` physical operator is requested for [filtered cached column batches](physical-operators/InMemoryTableScanExec.md#filteredCachedBatches) (as a `RDD[CachedBatch]`).

| isParquetBinaryAsString
| spark-sql-properties.md#spark.sql.parquet.binaryAsString[spark.sql.parquet.binaryAsString]
| [[isParquetBinaryAsString]]

| isParquetINT96AsTimestamp
| spark-sql-properties.md#spark.sql.parquet.int96AsTimestamp[spark.sql.parquet.int96AsTimestamp]
| [[isParquetINT96AsTimestamp]]

| isParquetINT96TimestampConversion
| spark-sql-properties.md#spark.sql.parquet.int96TimestampConversion[spark.sql.parquet.int96TimestampConversion]
| [[isParquetINT96TimestampConversion]] Used exclusively when `ParquetFileFormat` is requested to [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues).

| joinReorderEnabled
| spark-sql-properties.md#spark.sql.cbo.joinReorder.enabled[spark.sql.cbo.joinReorder.enabled]
| [[joinReorderEnabled]] Used exclusively in spark-sql-Optimizer-CostBasedJoinReorder.md[CostBasedJoinReorder] logical plan optimization

| limitScaleUpFactor
| spark-sql-properties.md#spark.sql.limit.scaleUpFactor[spark.sql.limit.scaleUpFactor]
| [[limitScaleUpFactor]] Used exclusively when a physical operator is requested SparkPlan.md#executeTake[the first n rows as an array].

| manageFilesourcePartitions
| hive/configuration-properties.md#spark.sql.hive.manageFilesourcePartitions[spark.sql.hive.manageFilesourcePartitions]
a| [[manageFilesourcePartitions]][[HIVE_MANAGE_FILESOURCE_PARTITIONS]] Used when:

* `HiveMetastoreCatalog` is requested to hive/HiveMetastoreCatalog.md#convertToLogicalRelation[convert a HiveTableRelation to a LogicalRelation over a HadoopFsRelation]

* <<spark-sql-LogicalPlan-CreateDataSourceTableCommand.md#, CreateDataSourceTableCommand>>, <<spark-sql-LogicalPlan-CreateDataSourceTableAsSelectCommand.md#, CreateDataSourceTableAsSelectCommand>> and [InsertIntoHadoopFsRelationCommand](logical-operators/InsertIntoHadoopFsRelationCommand.md) logical commands are executed

* `DDLUtils` utility is used to spark-sql-DDLUtils.md#verifyPartitionProviderIsHive[verifyPartitionProviderIsHive]

* `DataSource` is requested to [resolve a relation](DataSource.md#resolveRelation) (for file-based data source tables and creates a `HadoopFsRelation`)

* `FileStatusCache` is requested to `getOrCreate`

| metastorePartitionPruning
| spark-sql-properties.md#spark.sql.hive.metastorePartitionPruning[spark.sql.hive.metastorePartitionPruning]
a| [[metastorePartitionPruning]][[HIVE_METASTORE_PARTITION_PRUNING]] Used when hive/HiveTableScanExec.md[HiveTableScanExec] physical operator is executed with a partitioned table (and requested for HiveTableScanExec.md#rawPartitions[rawPartitions])

| minNumPostShufflePartitions
| <<spark-sql-properties.md#spark.sql.adaptive.minNumPostShufflePartitions, spark.sql.adaptive.minNumPostShufflePartitions>>
a| [[minNumPostShufflePartitions]] Used exclusively when [EnsureRequirements](physical-optimizations/EnsureRequirements.md) physical optimization is executed (for [Adaptive Query Execution](new-and-noteworthy/adaptive-query-execution.md)).

| offHeapColumnVectorEnabled
| [spark.sql.columnVector.offheap.enabled](spark-sql-properties.md#spark.sql.columnVector.offheap.enabled)
a| [[offHeapColumnVectorEnabled]] Used when:

* `InMemoryTableScanExec` is requested for the [vectorTypes](physical-operators/InMemoryTableScanExec.md#vectorTypes) and the [input RDD](physical-operators/InMemoryTableScanExec.md#inputRDD)

* `OrcFileFormat` is requested to [build a data reader with partition column values appended](OrcFileFormat.md#buildReaderWithPartitionValues)

* `ParquetFileFormat` is requested for [vectorTypes](ParquetFileFormat.md#vectorTypes) and [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues)

| optimizerInSetConversionThreshold
| spark-sql-properties.md#spark.sql.optimizer.inSetConversionThreshold[spark.sql.optimizer.inSetConversionThreshold]
| [[optimizerInSetConversionThreshold]] Used exclusively when `OptimizeIn` logical query optimization is spark-sql-Optimizer-OptimizeIn.md#apply[applied to a logical plan] (and replaces an spark-sql-Expression-In.md[In] predicate expression with an spark-sql-Expression-InSet.md[InSet])

|
|
a| [[ORC_IMPLEMENTATION]]

Supported values:

* `native` for [OrcFileFormat](OrcFileFormat.md)
* `hive` for `org.apache.spark.sql.hive.orc.OrcFileFormat`

| parallelFileListingInStatsComputation
| <<spark-sql-properties.md#spark.sql.statistics.parallelFileListingInStatsComputation.enabled, spark.sql.statistics.parallelFileListingInStatsComputation.enabled>>
a| [[parallelFileListingInStatsComputation]] Used exclusively when `CommandUtils` helper object is requested to <<calculateTotalSize, calculate the total size of a table (with partitions)>> (for <<spark-sql-LogicalPlan-AnalyzeColumnCommand.md#, AnalyzeColumnCommand>> and <<spark-sql-LogicalPlan-AnalyzeTableCommand.md#, AnalyzeTableCommand>> commands)

| parquetFilterPushDown
| spark-sql-properties.md#spark.sql.parquet.filterPushdown[spark.sql.parquet.filterPushdown]
| [[parquetFilterPushDown]] Used exclusively when `ParquetFileFormat` is requested to [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues).

| parquetFilterPushDownDate
| <<spark-sql-properties.md#spark.sql.parquet.filterPushdown.date, spark.sql.parquet.filterPushdown.date>>
| [[parquetFilterPushDownDate]] Used exclusively when `ParquetFileFormat` is requested to [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues).

| parquetRecordFilterEnabled
| spark-sql-properties.md#spark.sql.parquet.recordLevelFilter.enabled[spark.sql.parquet.recordLevelFilter.enabled]
| [[parquetRecordFilterEnabled]] Used exclusively when `ParquetFileFormat` is requested to [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues).

| parquetVectorizedReaderBatchSize
| <<spark-sql-properties.md#spark.sql.parquet.columnarReaderBatchSize, spark.sql.parquet.columnarReaderBatchSize>>
a| [[parquetVectorizedReaderBatchSize]] Used exclusively when `ParquetFileFormat` is requested for a [data reader](ParquetFileFormat.md#buildReaderWithPartitionValues) (and creates a [VectorizedParquetRecordReader](spark-sql-VectorizedParquetRecordReader.md) for [Vectorized Parquet Decoding](spark-sql-vectorized-parquet-reader.md))

| parquetVectorizedReaderEnabled
| spark-sql-properties.md#spark.sql.parquet.enableVectorizedReader[spark.sql.parquet.enableVectorizedReader]
a| [[parquetVectorizedReaderEnabled]] Used when:

* `FileSourceScanExec` is requested for spark-sql-SparkPlan-FileSourceScanExec.md#needsUnsafeRowConversion[needsUnsafeRowConversion] flag

* `ParquetFileFormat` is requested for [supportBatch](ParquetFileFormat.md#supportBatch) flag and [build a data reader with partition column values appended](ParquetFileFormat.md#buildReaderWithPartitionValues)

| preferSortMergeJoin
| spark-sql-properties.md#spark.sql.join.preferSortMergeJoin[spark.sql.join.preferSortMergeJoin]
| [[preferSortMergeJoin]] Used exclusively in [JoinSelection](execution-planning-strategies/JoinSelection.md) execution planning strategy to prefer sort merge join over shuffle hash join.

| replaceDatabricksSparkAvroEnabled
| spark-sql-properties.md#spark.sql.legacy.replaceDatabricksSparkAvro.enabled[spark.sql.legacy.replaceDatabricksSparkAvro.enabled]
| [[replaceDatabricksSparkAvroEnabled]][[LEGACY_REPLACE_DATABRICKS_SPARK_AVRO_ENABLED]]

| replaceExceptWithFilter
| spark-sql-properties.md#spark.sql.optimizer.replaceExceptWithFilter[spark.sql.optimizer.replaceExceptWithFilter]
| [[replaceExceptWithFilter]][[REPLACE_EXCEPT_WITH_FILTER]] Used when spark-sql-Optimizer-ReplaceExceptWithFilter.md[ReplaceExceptWithFilter] is executed

| runSQLonFile
| spark-sql-properties.md#spark.sql.runSQLOnFiles[spark.sql.runSQLOnFiles]
a| [[runSQLonFile]] Used when:

* `ResolveRelations` is requested to [isRunningDirectlyOnFiles](logical-analysis-rules/ResolveRelations.md#isRunningDirectlyOnFiles)

* `ResolveSQLOnFile` is requested to [maybeSQLFile](logical-analysis-rules/ResolveSQLOnFile.md#maybeSQLFile)

| starSchemaDetection
| spark-sql-properties.md#spark.sql.cbo.starSchemaDetection[spark.sql.cbo.starSchemaDetection]
| [[starSchemaDetection]] Used exclusively in spark-sql-Optimizer-ReorderJoin.md[ReorderJoin] logical plan optimization (and indirectly in `StarSchemaDetection`)

| stringRedactionPattern
| spark-sql-properties.md#spark.sql.redaction.string.regex[spark.sql.redaction.string.regex]
a| [[stringRedactionPattern]] Used when:

* `DataSourceScanExec` is requested to spark-sql-SparkPlan-DataSourceScanExec.md#redact[redact sensitive information] (in text representations)

* `QueryExecution` is requested to [redact sensitive information](QueryExecution.md#withRedaction) (in text representations)

| subexpressionEliminationEnabled
| spark-sql-properties.md#spark.sql.subexpressionElimination.enabled[spark.sql.subexpressionElimination.enabled]
| [[subexpressionEliminationEnabled]] Used exclusively when `SparkPlan` is requested for SparkPlan.md#subexpressionEliminationEnabled[subexpressionEliminationEnabled] flag.

| supportQuotedRegexColumnName
| spark-sql-properties.md#spark.sql.parser.quotedRegexColumnNames[spark.sql.parser.quotedRegexColumnNames]
a| [[supportQuotedRegexColumnName]] Used when:

* [Dataset.col](Dataset-untyped-transformations.md#col) operator is used

* `AstBuilder` is requested to parse a <<spark-sql-AstBuilder.md#visitDereference, dereference>> and <<spark-sql-AstBuilder.md#visitColumnReference, column reference>> in a SQL statement

| targetPostShuffleInputSize
| <<spark-sql-properties.md#spark.sql.adaptive.shuffle.targetPostShuffleInputSize, spark.sql.adaptive.shuffle.targetPostShuffleInputSize>>
| [[targetPostShuffleInputSize]] Used when [EnsureRequirements](physical-optimizations/EnsureRequirements.md) physical optimization is executed (for [Adaptive Query Execution](new-and-noteworthy/adaptive-query-execution.md))

| truncateTableIgnorePermissionAcl
| spark-sql-properties.md#spark.sql.truncateTable.ignorePermissionAcl.enabled[spark.sql.truncateTable.ignorePermissionAcl.enabled]
| [[truncateTableIgnorePermissionAcl]][[TRUNCATE_TABLE_IGNORE_PERMISSION_ACL]] Used when spark-sql-LogicalPlan-TruncateTableCommand.md[TruncateTableCommand] is executed

| wholeStageEnabled
| spark-sql-properties.md#spark.sql.codegen.wholeStage[spark.sql.codegen.wholeStage]
a| [[wholeStageEnabled]] Used in:

* [CollapseCodegenStages](physical-optimizations/CollapseCodegenStages.md) to control codegen
* [ParquetFileFormat](ParquetFileFormat.md) to control row batch reading

| wholeStageFallback
| spark-sql-properties.md#spark.sql.codegen.fallback[spark.sql.codegen.fallback]
| [[wholeStageFallback]] Used exclusively when `WholeStageCodegenExec` is spark-sql-SparkPlan-WholeStageCodegenExec.md#doExecute[executed].

| wholeStageMaxNumFields
| spark-sql-properties.md#spark.sql.codegen.maxFields[spark.sql.codegen.maxFields]
a| [[wholeStageMaxNumFields]] Used in:

* [CollapseCodegenStages](physical-optimizations/CollapseCodegenStages.md) to control codegen
* [ParquetFileFormat](ParquetFileFormat.md) to control row batch reading

| wholeStageSplitConsumeFuncByOperator
| spark-sql-properties.md#spark.sql.codegen.splitConsumeFuncByOperator[spark.sql.codegen.splitConsumeFuncByOperator]
| [[wholeStageSplitConsumeFuncByOperator]] Used exclusively when `CodegenSupport` is requested to [consume](physical-operators/CodegenSupport.md#consume)

| wholeStageUseIdInClassName
| spark-sql-properties.md#spark.sql.codegen.useIdInClassName[spark.sql.codegen.useIdInClassName]
| [[wholeStageUseIdInClassName]] Used exclusively when `WholeStageCodegenExec` is requested to <<spark-sql-SparkPlan-WholeStageCodegenExec.md#doCodeGen, generate the Java source code for the child physical plan subtree>> (when <<spark-sql-SparkPlan-WholeStageCodegenExec.md#creating-instance, created>>)

| windowExecBufferInMemoryThreshold
| spark-sql-properties.md#spark.sql.windowExec.buffer.in.memory.threshold[spark.sql.windowExec.buffer.in.memory.threshold]
| [[windowExecBufferInMemoryThreshold]] Used exclusively when `WindowExec` unary physical operator is <<spark-sql-SparkPlan-WindowExec.md#doExecute, executed>>.

| windowExecBufferSpillThreshold
| spark-sql-properties.md#spark.sql.windowExec.buffer.spill.threshold[spark.sql.windowExec.buffer.spill.threshold]
| [[windowExecBufferSpillThreshold]] Used exclusively when `WindowExec` unary physical operator is <<spark-sql-SparkPlan-WindowExec.md#doExecute, executed>>.

| useObjectHashAggregation
| spark-sql-properties.md#spark.sql.execution.useObjectHashAggregateExec[spark.sql.execution.useObjectHashAggregateExec]
| [[useObjectHashAggregation]] Used exclusively when [Aggregation](execution-planning-strategies/Aggregation.md) execution planning strategy is executed (and uses `AggUtils` to <<spark-sql-AggUtils.md#createAggregate, create an aggregation physical operator>>).
|===

=== [[getConfString]][[getConf]][[getAllConfs]][[getAllDefinedConfs]] Getting Parameters and Hints

You can get the current parameters and hints using the following family of `get` methods.

[source, scala]
----
getConf[T](entry: ConfigEntry[T], defaultValue: T): T
getConf[T](entry: ConfigEntry[T]): T
getConf[T](entry: OptionalConfigEntry[T]): Option[T]
getConfString(key: String): String
getConfString(key: String, defaultValue: String): String
getAllConfs: immutable.Map[String, String]
getAllDefinedConfs: Seq[(String, String, String)]
----

=== [[set]] Setting Parameters and Hints

You can set parameters and hints using the following family of `set` methods.

[source, scala]
----
setConf(props: Properties): Unit
setConfString(key: String, value: String): Unit
setConf[T](entry: ConfigEntry[T], value: T): Unit
----

=== [[unset]] Unsetting Parameters and Hints

You can unset parameters and hints using the following family of `unset` methods.

[source, scala]
----
unsetConf(key: String): Unit
unsetConf(entry: ConfigEntry[_]): Unit
----

=== [[clear]] Clearing All Parameters and Hints

[source, scala]
----
clear(): Unit
----

You can use `clear` to remove all the parameters and hints in `SQLConf`.

=== [[redactOptions]] Redacting Data Source Options with Sensitive Information -- `redactOptions` Method

[source, scala]
----
redactOptions(options: Map[String, String]): Map[String, String]
----

`redactOptions` takes the values of the <<spark-sql-properties.md#spark.sql.redaction.options.regex, spark.sql.redaction.options.regex>> and `spark.redaction.regex` configuration properties.

For every regular expression (in the order), `redactOptions` redacts sensitive information, i.e. finds the first match of a regular expression pattern in every option key or value and if either matches replaces the value with `*********(redacted)`.

NOTE: `redactOptions` is used exclusively when `SaveIntoDataSourceCommand` logical command is requested for the <<spark-sql-LogicalPlan-SaveIntoDataSourceCommand.md#simpleString, simple description>>.

## Accessing SQLConf

You can access a `SQLConf` using:

. <<get, SQLConf.get>> (preferred) - the `SQLConf` of the current active `SparkSession`

. <<SparkSession.md#sessionState, SessionState>> - direct access through <<SparkSession.md#sessionState, SessionState>> of the `SparkSession` of your choice (that gives more flexibility on what `SparkSession` is used that can be different from the current active `SparkSession`)

```text
import org.apache.spark.sql.internal.SQLConf

// Use type-safe access to configuration properties
// using SQLConf.get.getConf
val parallelFileListingInStatsComputation = SQLConf.get.getConf(SQLConf.PARALLEL_FILE_LISTING_IN_STATS_COMPUTATION)

// or even simpler
SQLConf.get.parallelFileListingInStatsComputation
```

```text
scala> :type spark
org.apache.spark.sql.SparkSession

// Direct access to the session SQLConf
val sqlConf = spark.sessionState.conf
scala> :type sqlConf
org.apache.spark.sql.internal.SQLConf

scala> println(sqlConf.offHeapColumnVectorEnabled)
false

// Or simply import the conf value
import spark.sessionState.conf

// accessing properties through accessor methods
scala> conf.numShufflePartitions
res1: Int = 200

// Prefer SQLConf.get (over direct access)
import org.apache.spark.sql.internal.SQLConf
val cc = SQLConf.get
scala> cc == conf
res4: Boolean = true

// setting properties using aliases
import org.apache.spark.sql.internal.SQLConf.SHUFFLE_PARTITIONS
conf.setConf(SHUFFLE_PARTITIONS, 2)
scala> conf.numShufflePartitions
res2: Int = 2

// unset aka reset properties to the default value
conf.unsetConf(SHUFFLE_PARTITIONS)
scala> conf.numShufflePartitions
res3: Int = 200
```
