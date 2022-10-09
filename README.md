# leetcode_graph_problem_2
Solution of Leetcode problem 981
class TimeMap {
public:
    map<string,set<pair<int,string> > > mp;
    TimeMap() {
        
    }
    
    void set(string key, string value, int timestamp) {
        mp[key].insert({timestamp,value});
    }
    
    string get(string key, int timestamp) {
        //return "";
        if(mp[key].size()==0){
            return "";
        }
        auto it=mp[key].end();
        do{
            it--;
            if((*it).first<=timestamp){
                return (*it).second;
            }
        }
        while(it!=mp[key].begin());
        return "";
    }
};

/**
 * Your TimeMap object will be instantiated and called as such:
 * TimeMap* obj = new TimeMap();
 * obj->set(key,value,timestamp);
 * string param_2 = obj->get(key,timestamp);
 */
