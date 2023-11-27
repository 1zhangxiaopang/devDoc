
````go

func BitToInt(b []byte) (int, error)
func BsonStrLongToString(s string) (resV string, rErr error)
func BsonToJsonStr(d any) (resV string, rErr error)
func ByteToFloat32(bytes []byte, isBigEndian bool) float32
func ByteToFloat64(bytes []byte, isBigEndian bool) float64
func ByteToUint16(array []byte) uint16
func BytesToHexString(src []byte) string
func BytesToInt(b []byte, isBigEndian bool) int
func BytesToInt64(buf []byte, isBigEndian bool) int64
func CheckFileIsExist(filename string) bool
func CheckPasswordComplexity(pwd string) bool
func CompressionStr(str string) string
func Concat(str *string, args ...string)
func ConcatR(args ...string) string
func ConvFileBase64(filePath, fileSuffix string) (string, error)
func CustStrReduction(value *string)
func CustStrReplace(value *string)
func CustUUID(ln int) string
func Decode(code string) (string, error)
func DecryPass(str string) (string, error)
func DeleteFile(filePath string) error
func EnCode(str string) string
func EncryPass(str string) (string, error)
func EscapeStr(str string) string
func Float32ToByte(float float32, isBigEndian bool) []byte
func Float64ToByte(float float64, isBigEndian bool) []byte
func FmtGjsonValue(v gjson.Result) string
func GeetSHA1Encode(str string) string
func Get16MD5Encode(data string) string
func GetCRC32Encode(str string) uint32
func GetCurrWeekByDate(t time.Time, mode int) string
func GetFileAbsPath(path string) (string, error)
func GetIfsType(ifs interface{}) string
func GetJSON(v interface{}) (string, error)
func GetJSONKeys(jsonStr *string) []string
func GetMACAddress() (string, error)
func GetMD5Encode(data string) string
func GetNextWeekByDate(t time.Time, mode int) string
func GetOBJ(jsonStr string, pointer interface{}) error
func GetSnowflakeID(workID int64) (int64, error)
func GetSnowflakeIDFmtStr(workID int64) (string, error)
func GetYearFirstWeekDays(year int, mode int) int
func GetYearLastWeekDays(year int, mode int) int
func GetYearSumWeeks(year int, mode int) int
func HostIPAddrCheck(addr string) bool
func HostPortCheck(port string) bool
func Int64ToBytes(i int64, isBigEndian bool) []byte
func IntToBytes(n int) []byte
func IsChinese(str string) bool
func JSONOBJAppend(json *gjson.Result, objStr string) error
func JSONOBJModify(json *gjson.Result, keyPath, NewValue string) error
func JsonStrToBson(str string) (BSON any, rErr error)
func JsonStrToBsonByte(str string) ([]byte, error)
func JsonStrToBsonFmtBigInt(str string) (any, error)
func JsonStrToMap(str string, mapPointer any) error
func MapToStruct(obj interface{}, mapping map[string]string) error
func ReadConfFile(path string) map[string]string
func RemoveContents(dir string) error
func StrMatches(str string, ignoreCase, isEqual bool, vs ...string) bool
func StrToInt64OfSnowID(gJSON gjson.Result) (raw string, rErr error)
func ToBsonBytes(stu interface{}) ([]byte, error)
func ToJsonBytes(stu interface{}) ([]byte, error)
func Uint16ToByte(n uint16) []byte
func UnZipStr(str string) (string, error)
func UnicodeIndex(str, subStr string) int
func WriteMaptoFile(m map[string]string, filePath string) error
func ZipStr(str string) (string, error)
````


