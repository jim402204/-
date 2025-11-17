# -

protocol AutoPrint: CustomStringConvertible {}

extension AutoPrint {
    var description: String {
        let mirror = Mirror(reflecting: self)
        var result = "\(type(of: self))("
        let children = mirror.children.map { "\($0.label!): \($0.value)" }
        result += children.joined(separator: ", ")
        result += ")"
        return result
    }
}

